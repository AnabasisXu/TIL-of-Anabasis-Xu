#+TITLE:      Using Emacs within VScode
#+DATE:       [2024-02-23 Fri 10:13]
#+FILETAGS:   :tooling:
#+IDENTIFIER: 20240223T101356
#+SOURCE: 


I recently started to learn web development with Emacs. Emmet-mode has been great, until one day it reports:

```elisp
Debugger entered&#x2013;Lisp error: (void-function first)
  (first expr)
  (if (first expr) (list (first expr) start end))
  (let\* ((end (point)) (start (emmet-find-left-bound)) (line (buffer-substring-no-properties start end)) (expr (emmet-regex "\\$[ \11]*\$\\$[^\n]+\$" line 2))) (if (first expr) (list (first expr) start end)))
  emmet-expr-on-line()
```

I just could not find anywhere in the emmet.el file that the function `first` is undefined. I tried loading the file with a clean setup with `runemacs -Q`, then I was surprised to find that it worked just fine. Eventually, it turns out that `first` should be `cl-first`, as with `second`, `third`, and so on. For the more recent versions of Emacs, there is a reminder that says "cl is obsolete" to encourage the user to change and replace it with `cl-lib`. Unfortunately, no such reminder exists for `first`.

Before figuring out the cause, I decided that I did not have the time for that. I just needed to move on to something that works out of the box. The ideal of living in Emacs presumes proficiency with the Lisp language, a requirement I can only satisfy only in the future. 

I went back to my old VS Code powered by Neovim, but the editing experience is far inferior to my Evil mode setup. So I tried to google "use emacs with vscode" and stumbled on exactly what I need: [Configuring VSCode as a Keyboard-Centric IDE | Davis Haupt](https://davi.sh/blog/2023/01/vscode-like-emacs/). 

A few quick reminders for new users: 

1.  First install Vim. In my case, I use `scoop install vim`.
2.  After installing the plugin [VSpaceCode | VSpaceCode](https://vspacecode.github.io/), you are prompted with the option of either manual or automatic configuration. If you misclicked the manual configuration, then `spc` with not trigger the `which-key` interface. Instead of reinstalling the plugin, just run `VSpaceCode: Configure Default Settings and Keybindings` to complete the auto setup.
3.  Get familiar with the default keybindings at [Default Keybindings | VSpaceCode](https://vspacecode.github.io/docs/default-keybindings).
4.  The commands in the [Conventions | VSpaceCode](https://vspacecode.github.io/docs/conventions) section may require extensions in the [Major Mode | VSpaceCode](https://vspacecode.github.io/docs/major-mode) section.

