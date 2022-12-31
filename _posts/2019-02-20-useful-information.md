---
layout: post
title:  "Dotfiles Useful information"
date:   2019-02-20 13:00:00 +0800
categories: tutorials
---
## Commands
Find and replace with sed in directory and sub directories ignoring hidden directories and files in the root folder
```
find . -not -path './\.*' -type f -exec sed -i '' 's/apple/orange/g' {} \;
```

## tmux Date/Time values in the status line
$(echo $USER) - shows the current username
%a --> Day of week (Mon)
%A --> Day of week Expanded (Monday)

%b --> Month (Jan)
%d --> Day (31)
%Y --> Year (2017)

%D --> Month/Day/Year (12/31/2017)
%v --> Day-Month-Year (31-Dec-2017)

%r --> Hour:Min:Sec AM/PM (12:30:27 PM)
%T --> 24 Hour:Min:Sec (16:30:27)
%X --> Hour:Min:Sec (12:30:27)
%R --> 24 Hour:Min (16:30)
%H --> 24 Hour (16)
%l --> Hour (12)
%M --> Mins (30)
%S --> Seconds (09)
%p --> AM/PM (AM)

For a more complete list view: https://linux.die.net/man/3/strftime

## VIM
### Short-forms
- au = autocmd
- et = expandtab
- ft = filetype
- lbr = linebreak
- setl = setlocal
- sw = shiftwidth
- ts = tabstop
- tw = textwidth

## ZSH key bindings
- ctrl-a = Beginning of line
- ctrl-e = End of line
- ctrl-w = Delete the previous word
- alt-b = Move one word backward
- alt-f = Move one word forward

## References
- [vim-plug](https://github.com/junegunn/vim-plug)
- [vim-go](https://github.com/fatih/vim-go)
- [Thoughtbot dotfiles](https://github.com/thoughtbot/dotfiles)
- [zsh vcs_info-examples](https://github.com/zsh-users/zsh/blob/master/Misc/vcs_info-examples)
- [Shortcuts for zsh](http://www.geekmind.net/2011/01/shortcuts-to-improve-your-bash-zsh.html)
- [A Note About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [Spell Check in vim](http://thejakeharding.com/tutorial/2012/06/13/using-spell-check-in-vim.html)
- [No Newline at End of File](https://thoughtbot.com/blog/no-newline-at-end-of-file)
- [oh-my-zsh git shortcuts](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/git)
