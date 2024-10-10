Back to [[FJSx23]] / [[Node.js]]
### What is it?
Small third-party extension for Node to help with configuration management and security.

Installation:
`npm install dotenv`
##### Benefits

- `.env` files allow you to define environment-specific variables in a centralized location. This makes it easy to manage different settings for different environments (e.g., development, testing, production) without changing the application code.
- Storing sensitive information such as API keys, database credentials, and other secrets in a `.env` file helps to keep them out of your source code. This reduces the risk of accidentally exposing sensitive information in version control systems like Git.
- By using `.env` files, you separate configuration from code. This adheres to the principle of separation of concerns, making your application easier to manage and more modular.
- Managing environment variables via `.env` files is straightforward and supported by various libraries like `dotenv` in Node.js, which makes loading these variables into your application simple.

```python
# .env
PORT=3000 
DATABASE_URL=mongodb://localhost:27017/myapp 
SECRET_KEY=mysecretkey
```

```javascript
// app.js

import dotenv from "dotenv";

dotenv.config(); // Initiates environment variables so they are available in your app

const express = require('express');
const app = express();

const PORT = process.env.PORT || 3000;

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});

// Now you can use process.env to access your variables
const dbUrl = process.env.DATABASE_URL;
const secretKey = process.env.SECRET_KEY;
```
