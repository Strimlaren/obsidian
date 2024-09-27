Back to [[FJSx23]] / [[Node.js]] / [[MongoDB]]
### What is it?
Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js. It provides a straightforward, schema-based solution to model your application data. It includes built-in type casting, validation, query building, business logic hooks, and more. Mongoose helps in managing relationships between data, provides schema validation, and is used to translate between objects in code and the representation of those objects in MongoDB.

Installation: 
`npm install mongoose`

##### Connecting mongoose to MongoDB database
```javascript
import mongoose from "mongoose";

   mongoose.connect('mongodb://localhost/mydatabase',       // MongoDB server URI
		{ useNewUrlParser: true, useUnifiedTopology: true }) // Avoid deprecation errors
  .then(() => console.log('MongoDB connected...'))
  .catch(err => console.log(err));
```
##### Defining a mongoose Schema
```javascript
const Schema = mongoose.Schema; 

const userSchema = new Schema({ 
	name: { type: String, required: true }, 
	email: { type: String, required: true, unique: true }, 
	age: Number, 
	created_at: { type: Date, default: Date.now },
	},	{timestamps: true}
);
```
##### Defining a model based on Schema
```javascript
const User = mongoose.model('User', userSchema); // Name of collection for this Schema
```
##### Creating and saving a new model to the collection
```javascript
const newUser = new User({
  name: 'John Doe',
  email: 'john.doe@example.com',
  age: 30
});

newUser.save()
  .then(user => console.log(user))
  .catch(err => console.log(err));
```