---
title: Javascript random integer without rounding
date: 2020-07-25
tags: javascript
---

To random numbers between 0 to n, normally people would use:

```javascript
Math.floor(Math.random() * (n+1))
```

Do this instead:

```javascript
~~(Math.random() * (n+1))
```

`~~` is a double NOT bitwise operator. 
They're faster than `Math.floor()`, but be noted that the result are not always the same.


