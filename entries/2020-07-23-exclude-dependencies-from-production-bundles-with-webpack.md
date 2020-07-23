---
title: Exclude dependencies from production bundles with Webpack
date: 2020-07-23
tags: javascript, webpack
---

Use case : Want to develop with a library (say, jQuery) but want to use jQuery from CDN in production mode.

webpack.production.js:

```javascript
module.exports = {
  mode: 'production',
  //...
  externals: {
    jquery: 'jQuery'
  }
};
```

Reference : https://webpack.js.org/configuration/externals/
