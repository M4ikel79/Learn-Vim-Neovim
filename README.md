# Learn-Vim-Neovim

[![Vim](https://img.shields.io/badge/Vim-Editor-brightgreen?style=flat&logo=vim&logoColor=white)](https://www.vim.org) [![Neovim](https://img.shields.io/badge/Neovim-Editor-3DA55F?style=flat&logo=neovim&logoColor=white)](https://neovim.io)

A repo containing curated Vim and Neovim help files, examples, and tips to learn and reference Vim/Neovim features and configuration. Files are intended to be readable in a browser or installed into your editor's runtime to be available via :help.

## Table of contents
- About
- Repository structure
- Quick start
- Installing help files (Vim & Neovim)
- Viewing the help locally
- Contributing
- License
- Contact / Support

## About
This repository collects help files, mini-guides, and example configs to help users learn Vim and Neovim. Help files are formatted so they can be used with Vim's :help system (when placed in a doc/ directory and processed with helptags) and are also viewable as plain text or HTML in a browser.

## Repository structure
(Adjust if your repo uses different folders)
- docs/ or help/ — raw help files (text or HTML)
- examples/ — example vimrc / init.lua snippets
- tips/ — short how-to notes and shortcuts
- README.md — this file

## Quick start
Clone the repo:

```
git clone https://github.com/M4ikel79/Learn-Vim-Neovim.git
cd Learn-Vim-Neovim
```

Open HTML help files in your browser (if present):

```
# from repo root, open index.html or individual .html files
# e.g. (Linux)
xdg-open docs/index.html   # or open on macOS with `open`
```

Recommended: run a local static server with live-server
- Open the directory that contains the HTML help files (for example docs/ or help/) — or open the repo root if the HTML files are in the root.
- Run once without installing globally:
```
npx live-server
```
- Or install live-server via npm:
```
# install globally
npm install -g live-server
# or add as a dev dependency
npm install --save-dev live-server
```
- Then run:
```
live-server
```

This starts a local server (e.g. http://127.0.0.1:8080) so you can browse the help in your browser. Opening the directory "between the two" and running `npx live-server` (as you prefer) is the recommended workflow for this repo.

Or open the text help files directly in Vim/Neovim after installing (see below).

## Installing help files into Vim / Neovim
If you want these help files available via :help inside Vim/Neovim, copy them into your editor's doc directory and generate helptags.

For Vim (classic):
1. Copy help files to ~/.vim/doc/ (create if missing)
2. In Vim run:
```
:helptags ~/.vim/doc
```

For Neovim:
1. Copy help files to ~/.local/share/nvim/site/doc/ (or to a plugin's doc/ directory under your runtimepath)
2. In Neovim run:
```
:helptags ALL
```
Or generate helptags from the shell:
```
nvim --headless +'helptags ALL' +qa
```

Notes:
- Help file names should end with .txt and include a tag line (see Vim help file format).
- If you place files inside a plugin folder under pack/*/start/, they are picked up automatically by runtimepath; then run :helptags on that doc directory.

## Viewing the help locally
- Text help files: open directly in Vim/Neovim with :help {tag} after generating helptags.
- HTML files: open in any browser or use live-server as recommended above.
- Quick search: use grep or ripgrep inside the repo:
```
rg "search-term" .
```

## Contributing
Contributions welcome.
- Add new help files in docs/ or help/.
- If adding a Vim help file (.txt), include tags and a short summary line.
- Run tests / validate formatting manually (there are no automated checks yet).
- Submit a pull request with a clear title and description.
- Coding style: keep examples minimal and annotated.

Suggested PR checklist:
- [ ] File placed in correct folder
- [ ] Help/tags formatted for :helptags if appropriate
- [ ] Examples tested in Vim/Neovim

## License
This repository is released under the MIT License — see the included LICENSE file for details.

## Contact / Support
For issues or feature requests, open an issue in this repository: https://github.com/M4ikel79/Learn-Vim-Neovim/issues
