Back to [[FJSx23]] / [[Node.js]]
### What is it?
Module for creating and handling a Node server.

##### createServer( ) & listen( )

```js
let server = createServer((request, response) => {
  response.write(html);
});

server.listen(3000);
```

Also, a shorthand can be used in [[Express.js]]
```javascript
import express from "express";
let app = express();

app.get("/", (req,res) => {
	res.send("Successfully hit home.");
})

app.listen(3000);
```