## Atomic-chrome + GhostText for great editing experience in Chromium

Today I need to use some simple HTML script in a reply to a GitHub issue. Tried the built-in ACE editor of [https://chromewebstore.google.com/detail/surfingkeys/gfbliohnnapiefjpjlpjnehglfpaknnc](Surfingkeys). Having a Vim editor directly in your browser is nice, I but two things are bugging me:
1. The text area is too small
2. No support for surround editing for tags.
3. Easy to mistype ESC, losing the focus on the editor. Then you have to click it to make focus come back to it.

  * [ ] I used to have Firenvim which is quite nice, but now that most of my text editing happens in Emacs, I want to find an equivalent to Firenvim in Emacs. Turns out that [https://github.com/alpha22jp/atomic-chrome](alpha22jp/atomic-chrome: Edit text area on Chrome with Emacs using Atomic Chrome) + [https://chromewebstore.google.com/detail/ghosttext/godiecgffnchndlihlpaajjcplehddca?pli=1](GhostText) is exactly what I need.

** Install atomic-chrome

Just the most basic configuration from the Readme.

```elisp
(use-package atomic-chrome
  :straight (atomic-chrome
             :type git
						 :host github
						 :repo "alpha22jp/atomic-chrome")
	:init
	(require 'atomic-chrome)
	(atomic-chrome-start-server)
	:config
	;; Disable auto-update. In this case, you can apply the modifications to the browser with C-c C-s
	(setq atomic-chrome-enable-auto-update nil)
	(setq atomic-chrome-default-major-mode 'markdown-mode)
	(setq atomic-chrome-url-major-mode-alist
				'(("github\\.com" . gfm-mode)
					("redmine" . textile-mode)))
	;; (setq atomic-chrome-server-ghost-text-port 4002)
	;; (setq atomic-chrome-extension-type-list '(atomic-chrome))
	
	)

```


** Install GhostText

Install GhostText at [https://chromewebstore.google.com/detail/ghosttext/godiecgffnchndlihlpaajjcplehddca?pli=1](GhostText) 

Uncheck the "Display notifications when connected and disconnected" which is annoying, but keep the "Bring the focus back to the browser when disconnected." which is useful.

I use Surfingkeys in which one goes to the editing area by Ctrl+i, so I set up the shortcut for activating GhostText to Alt+i to keep the flow.


