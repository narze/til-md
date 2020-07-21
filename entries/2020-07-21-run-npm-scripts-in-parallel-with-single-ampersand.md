---
title: Run npm scripts in parallel with single &
date: 2020-07-21
tags: nodejs
---

```json
{ 
  "scripts": {
    "dev": "webpack --watch & postcss --watch & eleventy --serve"
  }
}
```
