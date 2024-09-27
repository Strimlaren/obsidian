Back to [[FJSx23]]
### What is it?
MongoDB is a NoSQL type database most oftenly used together with Node.js. 
##### MongoDB (NoSQL) vs Relational (SQL) Databases
SQL databases that are relational work with tables. This means that data cannot be nested like in a NoSQL databases, but instead, one must relate to other tables to "nest", like in the figure below. NoSQ databases will not complain if documents (database entries) inside collections (tables) dont have the same contents as the next one. Inside the same collection, two documents can coexist and contain no overlapping key-value pairs or data overall. Often [[mongoose]] is used as a wrapper plugin to increase ease of use between the Node application and the MongoDB server.

![[mongodb1.png]]

