---
title: Create array with numbers 1 to N in Javascript
date: 2020-09-18
tags: javascript
---

Use Array constructure with `fill` to enable array mapping

```javascript
const n = 100

Array(n).fill().map((_, i) => i + 1)

// => [1, 2, 3, ..., 100]
```

If start from 0, use `keys()` and spread them

```javascript
[...Array(n).keys()]

// => [0, 1, 2, ..., 99]
```

Ref: https://stackoverflow.com/questions/3746725/how-to-create-an-array-containing-1-n
