Back to [[FJSx23]] / [[Node.js]]
### What is it?
Make static files inside the public folder available as routes and/or resources inside the serverside rendered content.

```javascript
let express = require('express');
let app = express();

//setting middleware
app.use(express.static(__dirname + 'public')); 

let server = app.listen(5000);
```