---
title: Ruby Squiggly Heredoc
date: 2020-07-21
tags: ruby
---

Squiggly heredoc is a heredoc syntax but will remove indentations for every line, so it can align with surrounding code.

```ruby
<<~EOF
    Indent all you want
    <~ Squiggly heredoc strips them all
EOF
```
