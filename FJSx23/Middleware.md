Back to [[FJSx23]] / [[Express.js]]
### What is it?
Middleware is a function that takes the users request and runs some code on it, and when it is done, next( ) is called to tell Express that the middleware is done processing so the next request handler in line can be called.

```javascript
import express from "express";

const app = express();

app.use(express.json());
app.use(loggingMiddleware);  // Using middleware globally, for all API calls

const loggingMiddleware = (request, response, next) => {
	console.log(`${request.method} - ${request.url}`)
}

// Using it as an optional parameter inside any API calls
app.get("/api/users", loggingMiddleware, (request, response) => {
	response.status(201).send({msg: "Hello" });
})

// Chaining middlewares like async await .then() method calls.
app.get("/api/users", (req, res, next) => {
		console.log("URL 1");
		next();
	}, 
	(req, res, next) => {
		console.log("URL 2");
		next();
	},
	(req, res, next) => {
		console.log("URL 3");
		next();
	},
	(req, res) => {
	res.status(201).send({msg: "Hello" });
})


```

**NOTE:** Middlewares must be registered with `app.use()` BEFORE they are called.


The `app.use()` method has an optional parameter for filtering on paths. If passed, the middleware will only run if call path matches.
```javascript

app.use("/example", (req, res, next) => {
	req.myVariable = "Some random stuff you need to pass on.";
	next();
})

```