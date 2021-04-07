---
title: Parse timestamp to human-friendly date format in command line
date: 2021-04-07
tags: cli
---

Some CLI commands return Unix timestamp like `1617800185`

Here's a quick way to parse it in command line

```bash
date -r 1617800185

# => Wed Apr  7 19:56:25 +07 2021
```
