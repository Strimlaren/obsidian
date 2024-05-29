Back to [[FJSx23]] / [[Node.js]]
### What is it?
The [sendFile()](https://www.geeksforgeeks.org/express-js-res-sendfile-function/) function in Express.js is used to send the file in response to the HTTP request which is done by the client. This function takes the absolute path of the file as the argument and the file which is used to be sent to the client.

```javascript
const express = require('express');
const app = express();
const path = require('path');
const PORT = 3000;
// route
app.get('/', function (req, res, next) {
    const op = {
        root: path.join(__dirname)
    };
    // sending file
    const gfgFile = 'gfg.txt';
    res.sendFile(gfgFile, op, function (error) {
        if (error) {
            next(error);
        } else {
            console.log('File Sent is:', gfgFile);
        }
    });
});
app.listen(PORT, function (err) {
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```