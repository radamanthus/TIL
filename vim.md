# Vim

## Install Vundle and plugins

Download Vundle
`git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`

Then `vim ~/.vimrc`
and run `:PluginInstall` 

## Basics

#### Navigation

From: https://vim.fandom.com/wiki/Moving_around

Go to next word: `w`
Go to previous word: `b`
Go to next character: `l`
Go to previous character: `h`
Go to next line: `j`
Go to previous line: `k`
Go to the end of the line: `$`
Go to the start of the line: `^`
Go to the first non-blank character in the line: `0`
Go to next sentence: `)`
Go to previous sentence: `(`
Go to the next paragraph: `}`
Go to the previous paragraph: `{`
Go to the start of the file: `gg`
Go to the end of the file: `G`

#### Editing

Undo: `u`
Redo: `Ctrl-r`
Repeat previous change: `.`

Type a Unicode character:
- Go to Insert mode
- Ctrl-v to go to ins-special-keys mode
- u<unicode number> (e.g. 2713 to type a check mark)

#### Search

Search within the document: `/` then type the search string
Project-wide search: `:Ag <search string>` - this requires the Silver Searcher
TODO: Setup `fzf and Rg`

#### Selection

Select word: `yw`
Select line: `yy`
Select paragraph: `vip`
Go to visual selection mode: `v` to select by character or word, `V` to select by line

## Convert Tabs to Spaces

Add to vimrc:

```
set tabstop=2
set shiftwidth=2
set expandtab
```

Then do a `retab`

http://vim.wikia.com/wiki/Converting_tabs_to_spaces

## Useful shortcuts from YADR

gf - Open the class/file under the cursor
vsplit - split vertically. Use Ctrl-l and Ctrl-h to move between windows



