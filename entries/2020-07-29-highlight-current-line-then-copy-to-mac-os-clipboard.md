---
title: Highlight current line then copy to macOS clipboard
date: 2020-07-29
tags: vim, macos
---

First, set vimrc to handle <C-c> for copy & <C-v> for paste
```vimrc
vmap <C-c> y:call system("pbcopy", getreg("\""))<CR>
 nmap <C-v> :call setreg("\"",system("pbpaste"))<CR>p
```

Use `V` <Shift-v> to highlight current line in cursor then use <C-c> to copy highlight selection both to Vim's registry & macOS clipboard via `pbcopy`
Use <C-v> to paste from Normal mode

