---
title: BASH & VIM TIPS AND TRICKS
date: 2020-05-10 17:43:02
tags: [MacOS, Linux, BASH, VIM, TRICK]
comment: true
---

# SHELL & VIM TIPS
## Delete all the files except the exact file wanted to keep
```shell
ls | grep -v “fileName” | xargs rm
```
ls: list all the filename passing the filter set by grep.
grep: use regular expression to match files with “fileName”. ( -v: exclude this filename)
args: passing the arguments got previously to the command after.

## Delete files which filename has some pattern
For example, filename *ABC10_1*, *ABC10_2*, *ABC11_1*, *ABC11_2*,…
We want to delete files have the prefix from *ABC20* to *ABC30*

```shell
rm ABC{20..30}*
```

<!-- more -->

## Count how many files in one directory
```
ls -1 | wc -l
```
ls: list files in dir

-1: (that's a ONE) only one entry per line. Change it to -1a if you want hidden files too

|: pipe output onto...

wc: "wordcount"

-l: count lines.
## Vim basic search and replace
[Search and replace | Vim Tips Wiki | Fandom](https://vim.fandom.com/wiki/Search_and_replace)


## Useful shortcuts in Terminal
[The Best Keyboard Shortcuts for Bash (aka the Linux and macOS Terminal)](https://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc/)
### Most useful
**Moving the Cursor**
* **Ctrl+A** or **Home**: Go to the beginning of the line.
* **Ctrl+E** or **End**: Go to the end of the line.
* **Alt+B**: Go left (back) one word.
* **Ctrl+B**: Go left (back) one character.
* **Alt+F**: Go right (forward) one word.
* **Ctrl+F**: Go right (forward) one character.
* **Ctrl+XX**: Move between the beginning of the line and the current position of the cursor. This allows you to press Ctrl+XX to return to the start of the line, change something, and then press Ctrl+XX to go back to your original cursor position. To use this shortcut, hold the Ctrl key and tap the X key twice.

- - - -
**Deleting Text**
* **Ctrl+D** or **Delete**: Delete the character under the cursor.
* **Alt+D**: Delete all characters after the cursor on the current line.
* **Ctrl+H** or **Backspace**: Delete the character before the cursor.

- - - -

**Fixing Typos**
* **Alt+T**: Swap the current word with the previous word.
* **Ctrl+T**: Swap the last two characters before the cursor with each other. You can use this to quickly fix typos when you type two characters in the wrong order.
* **Ctrl+_**: Undo your last key press. You can repeat this to undo multiple times.

