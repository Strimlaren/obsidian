Back to [[FJSx23]] / [[Express]]
### What is it?
A middleware built in Express that tells the Express app from where static (public) files should be served, like css and images, so that they dont need to be implicitly and individually imported.

```javascript
let express = require('express');
let app = express();

app.use(express.static(__dirname + 'public')); 

let server = app.listen(5000);
```
