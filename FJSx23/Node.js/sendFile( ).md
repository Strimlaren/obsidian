Back to [[FJSx23]] / [[Express]]
### What is it?
The [sendFile()](https://www.geeksforgeeks.org/express-js-res-sendfile-function/) method in Express.js is used to send the file in response to the HTTP request which is done by the client. This method takes the absolute path of the file as the argument and the file which is used to be sent to the client. It allows control over the response and enables conditional rendering when serving a specific file, in contrast to just serving with the [[static]] express method.

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

Sending a file with `sendFile()` requires that you serve it an absolute path, which look different on different OSs. To account for this difference and make the provided path universal, the [[path]] module is used. With `.join()` or other methods you can 
```javascript
res.sendFile(path.join(__dirname, "views", "add-product.html"));
```