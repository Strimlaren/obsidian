Back to [[FJSx23]] / [[Express]]
### What is it?
It is middleware that helps with validating fields and API calls within express. Validation requests can be called in a chain and schemas can be made to outsource them from the main code to save space and make code more readable. 

[Official Docs](https://express-validator.github.io/docs/)

Installation:
`npm install express-validator`
### Table of Contents:
- [[#The basic structure]]
- [[#Extracting errors from request body]]
- [[#Adding custom messages to checks]]
- [[#Validating specific parameters of request body]]
- [[#Checking for errors]]
- [[#Easily grabbing validated data only]]
- [[#Schemas for cleaner validation chaining]]
##### The basic structure:
How to import express-validator, and basic syntax for calling it as a middleware function before invoking the main request handler:
```javascript
// app.js

import { query } from "express-validator";

...

app.get("/", query("filter").isString().notEmpty() , (_request, _response) => {
	const { filter, value } = _request.query;

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})

```
##### Extracting errors from request body
When validator is called, it attaches a parameter to the request object called `context`. It contains many fields, and not all of them are relevant to us. We can manually grab that, but there is a built-in way inside express-validator that makes it easier for you. For this we import `validationResult` function and call it, passing it the request object, letting it extract the relevant parts for us and placing it in a variable of our choice.
```javascript
import { query, validationResult } from "express-validator"; // <---

...

app.get("/", query("filter").isString().notEmpty() , (_request, _response) => {
	const result = validationResult(_request);  // <---
	const { filter, value } = _request;

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```
##### Adding custom messages to checks
You can add custom error messages to each check by adding `.withMessage` after each one. This makes it easier for the API user or the developers to know which checks were failed.
```javascript
import { query, validationResult } from "express-validator";

...

app.get("/", query("filter").isString()
							.withMessage("Field must be a string!") // <---
							.notEmpty()
							.withMessage("Field must not be empty!"), // <---
							(_request, _response) => { 
	const result = validationResult(_request);  
	const { filter, value } = _request;

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```
##### Validating specific parameters of request body
In case of POST requests or similar request types where a body is sent, you can target specific keys from inside a json object sent in the request body and validate it. Multiple keys can be validated by middleware-chaining them, or grouping all validations inside an array.
```javascript
import { validationResult, body } from "express-validator"; // <---

...

app.post("/", body("userName").notEmpty()  // <---
							  .withMessage("Username must be specified!"), 
							  (_request, _response) => { 
	const result = validationResult(_request);  
	const { filter, value } = _request;

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```
##### Checking for errors
The express-validator built-in function `result.isEmpty()` will check if the result object returned from the validationResult variable contains errors or not. So if it is empty it is safe to assume the request item passed all validation checks. In this example, the errors will be returned as an array with the response.
```javascript
import { validationResult, body } from "express-validator"; 

...

app.post("/", body("userName").notEmpty()  
							  .withMessage("Username must be specified!"), 
							  (_request, _response) => { 
	const result = validationResult(_request);  
	const { filter, value } = _request;

	if(!result.isEmpty())                                    // <---
		_response.status(400).send({errors: result.array()}) // <---

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```
##### Easily grabbing validated data only
The `matchedData` function built-in to express validator will grab you the data from the request object that was validated. Oftentimes you will probably only be interested in using those values. This way you do not need to destruct and drill for the relevant data from the request object.
```javascript
import { body, 
		 validationResult, 
		 matchedData } from "express-validator"; // <---

...

app.post("/", body("userName").notEmpty()  
							  .withMessage("Username must be specified!"), 
							  (_request, _response) => { 
	const result = validationResult(_request);  
	const { filter, value } = _request;

	if(!result.isEmpty())                                    
		_response.status(400).send({errors: result.array()}) 

	const data = matchedData(request);  // <---

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```
##### Schemas for cleaner validation chaining
Instead of huge chains of validation checks in many places in the codebase, validation schemas can be set up in a separate file, imported and called as middleware, in the same place where the validation checks would normally be called. Schemas are regular objects.
```javascript
import { body,
		 validationResult,
		 matchedData,
		 checkSchema } from "express-validator"; // <---

import { userValidationSchema } from "./utils/validationSchemas"; // <---
...

app.post("/", checkSchema(userValidationSchema), (_request, _response) => {   // <---
	const result = validationResult(_request);  
	const { filter, value } = _request;

	if(!result.isEmpty())                                    
		_response.status(400).send({errors: result.array()}) 

	const data = matchedData(request);

	if (filter && value) 
		return _response.send(users.filter((user) => user[filter].includes(value)));
	return _response.status(200).send(users);
})
```

Validation schema data object structure example:
```javascript
// validationSchemas.js

export const userValidationSchema = {
	userName: {          // On top level, the body parameters expected are the keys
		isLength: {      // Checks are named the same as the validation methods
			options: {   // Optional options go here
				min: 5,
				max: 25,
			}
			errorMessage: "Username should be 5-25 characters long." // Error message
		}
		notEmpty: true,  // When options are not necessary, a simple boolean suffices
		isString {
			errorMessage: "Username must be a string."	
		},
	}
	passWord: {          // Second body parameter to be checked
		notEmpty: true,
		isLength: {
			options: {
				min: 8,
				max: 40,
			}
		}
	}
}
```