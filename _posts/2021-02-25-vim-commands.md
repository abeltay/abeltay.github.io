---
layout: post
title:  "VIM useful commands"
date:   2021-02-25 11:00:00 +0800
categories: tutorials
---
## Remove trailing whitespace
```
:%s/\s\+$//e
```
[Link](https://vim.fandom.com/wiki/Remove_unwanted_spaces)

## Convert the ^M linebreak to 'normal' linebreak in a file opened in vim
```
:e ++ff=dos
:set ff=unix
```
[Link](https://stackoverflow.com/questions/811193/how-to-convert-the-m-linebreak-to-normal-linebreak-in-a-file-opened-in-vim)

## Pretty print JSON
```
:%!python -m json.tool
```
[Link](https://pascalprecht.github.io/posts/pretty-print-json-in-vim/)
