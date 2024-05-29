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