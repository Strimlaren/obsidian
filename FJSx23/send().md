Back to [[FJSx23]] / [[Express]]
### What is it?
The `.send()` method can handle various types of responses and sets appropriate headers automatically. The `.send()` method automatically sets the `Content-Type` header based on the argument passed (e.g., `text/html` for HTML strings, `application/json` for JSON objects). By default, the status code is set to `200` (OK). You can set a different status code using the `.status()` method before calling `.send()`.

```javascript
const express = require('express');
const app = express();

const PORT = 3000;

app.get('/', (req, res) => {
  res.send('Hello, World!');
  res.send('<h1>Welcome to my homepage!</h1>');
  res.send({ message: 'Hello, World!', success: true });
  
});

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});

```