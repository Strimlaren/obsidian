Back to [[FJSx23]] / [[Node.js]]
### Why ES5 syntax instead of ES6+ ?
Node was originally designed using the CommonJS module syntax and is still widely used. Mostly because of legacy code and compatibility with older codebases.
```javascript
const path = require("path");
const express = require("express");

const router = express.Router();

router.get("/add-product", (req, res, next) => {
  res.send("ES5 imports/exports");
});

module.exports = router;
```

add-products.mjs:
```javascript
import path from "path";
import express from "express";

const router = express.Router();

router.get("/add-product", (req, res, next) => {
  res.send("ES5 imports/exports");
});

export default router;
```