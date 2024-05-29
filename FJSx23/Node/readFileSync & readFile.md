Back to [[FJSx23]] / [[Node.js]]
### What is it?
When you need to read the content of a file using NodeJS, you can use the built-in `fs` module which contains `readFile()` and `readFileSync()` methods. This tutorial will show you how to use both.

##### .readFileSync
```js
fs.readFileSync("./data.txt", "utf8");
// or
fs.readFileSync("./data.txt", { encoding: "utf8", flag: "r" });
```