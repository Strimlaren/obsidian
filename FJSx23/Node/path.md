Back to [[FJSx23]] / [[Node.js]]
### What is it?
The `path` module in Node.js provides utilities for working with file and directory paths. It offers a variety of methods to manipulate and handle file paths in a way that is consistent across different operating systems. This is particularly important because different operating systems have different conventions for file paths (e.g., Windows uses backslashes `\` while Unix-based systems like Linux and macOS use forward slashes `/`).

```javascript
const path = require('path');
const fullPath = path.join('users', 'joe', 'documents', 'file.txt');
console.log(fullPath); // 'users/joe/documents/file.txt' on Unix, 'users\joe\documents\file.txt' on Windows
```

##### Other Methods:
`.resolve()`
`.basename()`
`.dirname()`
`.extname()`
`.parse()`
`.format()`