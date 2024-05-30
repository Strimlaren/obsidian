Back to [[FJSx23]] / [[Express]]
### What is it?
This is a 3rd-party module that provides a middleware that will automatically recognize bodies inside requests, and automatically parse them so they are available inside your handler.

`npm install body-parser`

```javascript
const bodyParser = require("body-parser");

app.use(bodyParser.urlencoded({ extended: false }));
```