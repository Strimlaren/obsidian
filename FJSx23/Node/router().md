Back to [[FJSx23]] / [[Express]]
### What is it?
Hands tools for organizing routes in a neat way, and adds to separation of concerns. You can (and should) separate routes of the same domain into a separate file, and instead of attaching all api calls directly to app, you attach them to the router, which you then export from the file and import it inside app. A domain would be for example api/users and api/products. So you would separate all product related endpoints into a single router file and the same for users.

```javascript
// users.mjs

import { Router } from "express";

const router = Router();

router.get...

router.get...

router.post...

export default router;
```

```javascript
// app.mjs

import express from "express";
const app = express();

import { usersRouter } from "./routes/users.mjs";

app.use(usersRouter)

app.listen(3000);
```

To further clean up code, you can also create a separate file where all routes are gathered up, and then exporting that route, so all you need in your main app.mjs file would be one `use.(allMyRoutes)`.

```javascript
// index.mjs

import { Router } from "express";

import { usersRouter } from "./users.mjs";
import { productsRouter } from "./products.mjs";
import { adminRouter } from "./admin.mjs";
import { exampleRouter } from "./example.mjs";

const router = Router();

router.use(usersRouter);
router.use(productsRouter);
router.use(adminRouter);
router.use(exampleRouter);

export default router;
```

```javascript
// app.mjs

import express from "express";

const app = express();

import allMyRoutes from "./routes/index.mjs";
app.use(allMyRoutes);

app.listen(3000);
```