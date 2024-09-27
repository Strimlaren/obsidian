Back to [[FJSx23]] / [[Express]]
### What is it?
![[MVC.png]]
It is a pattern of building Node applications to make them more modular, easier to maintain, and scalable. 

[Official Docs](https://developer.mozilla.org/en-US/docs/Glossary/MVC)
##### Model example
Working with models in practice means you extract the business logic, i.e the handler function to a separate file, then import those functions into relevant routes files to be cleanly called as callback functions for each of their corresponding call route. All data handling like saving and loading data to and from files/json/variables/databases.
```javascript
// app.js

import express from "express";
const app = express();

import { productController } from "./controllers/productControllers.js";
import { shopController } from "./controllers/shopControllers.js";
...

app.get("/", shopController.getShop);

app.post("/admin", productController.postNewProduct);
```

```javascript
// shopControllers.js

export const getShop = (req, res, next) => {
	...
}
```

```javascript
// productControllers.js

export postNewProduct = (req, res, next) => {
	...
}
```

