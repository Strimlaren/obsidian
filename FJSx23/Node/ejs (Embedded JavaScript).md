Back to [[FJSx23]] / [[Express]]
### What is it?
The most popular templating engine for Express.js. Has some advantages and disadvantages to other templating engines. One of the advantages is the ability to use regular javascript in the middle of the HTML code that is to be served serverside. 

Install:
`npm install ejs --save`

```javascript
const express = require('express');
const app = express();
const path = require('path');

app.set('view engine', 'ejs'); // Set the engine to be used
app.set('views' path.join(__dirname, 'views'); // Set path to views files

app.get('/', (req, res) => {
    const data = {
        greeting: 'Hello',
        name: 'GFG'
    };
    res.render('index', data); // Send a specified view to the user
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server listening at http: //localhost:${PORT}`);
});
```

```javascript
<%- include("includes/head.ejs") %> // Insert content from head.ejs

  </head>
  <body>
  
    <%- include("includes/navigation.ejs") %> // Insert content from navigation.ejs

      <section class="card-container">
        <% for(let i=0; i < products.length; i++) { %>
          <% for(let k=0; k < products[i].items.length; k++) { %>
            <a class="none" href="/shop/product/<%= products[i].items[k].id %>">
              <article class="card">
                <h3>
                  <%= products[i].items[k].name %>
                </h3>
                <img src="<%= products[i].items[k].image %>" alt="N/A" />
                <p><span class="subtle">Category:</span>
                  <%= products[i].category.toUpperCase() %></p>
              </article>
            </a>
            <% } %>
         <% } %>
      </section>

      <%- include("includes/end.ejs") %> // Insert content from end.js
```

##### Syntax
Inserting variables
`<%= myVariable %>`

Inserting html from other ejs files for modularity:
`<%- include("relative/path/to/htmlFile.ejs") %>`

Enveloping JavaScript code anywhere inside ejs code must be enveloped by ejs tags on every line where it appears:
```javascript
<% for(let i=0; i < 10; i++) { %>
	<li>Item <%= data[i] %></li>
<% } %>
```