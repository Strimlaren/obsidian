Back to [[FJSx23]] / [[Express]]
### What is it?
Server side rendered content. Poor mans react.

```javascript
const express = require('express');
const app = express();
const path = require('path');

// Set EJS as the view engine
app.set('view engine', 'ejs');
app.set('views' path.join(__dirname, 'views');

// route to render a dynamic view
app.get('/', (req, res) => {
    const data = {
        greeting: 'Hello',
        name: 'GFG'
    };
    res.render('index', data);
});

// views directory


// start the server
const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server listening at http: `//localhost:${PORT}`);
});
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<title>Express Render Function</title>
</head>
<body>
	<h1>
		<%= greeting %>, <%= name %>!
	</h1>
</body>
</html>
```

```html

<!-- Refer to variables sent from handler -->
<%= myVariable %> 

<!-- Import other "components" EJS -->
<%- include("./path/toMy/componentEJSfile") %>

<!-- When using JS inside ejs, every line of JS must be surrounded by <% %> -->
<% for(let i = 0; i < myVariable.length; i++){ %>
	<li> List item <%= i %>
<% } %>

```