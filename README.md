## My Philosophy of Taking Notes

Hi, this is Anabasis Xu, a technical writer and translator. This repository focuses on the technical side of technical writing, though I also write about other topics that I find relevant. For example, I find it helpful to sort out the technical side of reading great books, which leads to the various book protocols.

I like both Emacs and Vim. I use Vim from within Emacs with [Evil Mode](https://github.com/emacs-evil/evil), and Emacs within Visual Studio Code with [VSpaceCode](https://github.com/VSpaceCode/VSpaceCode). My impression is that Emacs provides a superior editing experience, but Visual Studio Code is easier to set up.  

I write my notes with [Denote](https://protesilaos.com/emacs/denote), an Emacs package that follows consistent file metadata for note files. I lint my notes with [Vale](https://github.com/errata-ai/vale), which lints your prose with customizable styles. I use Vale with [vale-vscode](https://github.com/chrischinchilla/vale-vscode), as the VSpace interface makes it easier to filter linting reports and check which rule triggers a warning.

Note-taking, like everything else, takes time. Managing these notes takes even more. As the number of notes grows, so does the complexity of managing them. This is why most note-taking philosophies do not work for most people.

I believe the way to reduce the complexity that notes introduce is to take notes only when necessary, and only organize when necessary. I use a `worklog.org` for quick notes, which reduces note management to the minimum at the beginning. When some topics become too important to stay scattered in this `worklog.org`, then I collect them into this repository as an item of Today-I-Learned. Again, when I find TIL notes too simplistic, then I work on them further. The focus should always be on the work to do, not the note to take.
