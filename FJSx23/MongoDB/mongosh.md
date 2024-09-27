Back to [[FJSx23]] / [[MongoDB]]
### What is it?
Mongo Shell is MongoDBs own shell terminal. 

##### mongosh GENERAL commands

| command                                  | action                                                                                                                      |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `cls`                                    | Clear screen                                                                                                                |
| `db`                                     | Will show which database is currently selected                                                                              |
| `show dbs`                               | Will show all databases with at least one collection and one document                                                       |
| `show collections`                       | WIll show all collections of currently selected database                                                                    |
| `use dbName`                             | Will switch to database with dbName. If no such database exists, it will be created and set to currently selected database. |
| `db.createCollection("name", {options})` | Will create a new collection `name`, with `options`                                                                         |
| `db.collection.drop()`                   | Will delete the collection `collectionName`                                                                                 |
| `db.dropDatabase()`                      | Will delete database that is currently in use                                                                               |
##### mongosh INSERTING data commands

| command                          | action                                                                                                                                                                                                                         |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `db.test.insertOne({obj})`       | Creates a new collection `test` and inserts a new document with an entry with the contents of { Obj }.<br>**Note:** When creating a new document, if `_id` is not set explicitly, MongoDB will automatically add it implicitly |
| `db.test.insertMany([{},{},{}])` | Inserts many documents at the same time. Must be passed in as an array of objects                                                                                                                                              |

##### mongosh FINDING data commands
| command                            | action                                                                                                                                                                                                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `db.test.findOne({filter})`        | Finds the first occurence of the searched for object (like a filter). If no object is provided, will return the first document of the current collection.                                                                                                                |
| `db.test.find({filter},{exclude})` | Returns all occurences of the provided object (like a filter). If no filter object is provided, will return all objects in the collection. The `exclude` object can optionally be sent to tell the find method which fields to exclude in the returned array of results. |
| `...find({}).pretty()`             | To get the results from the find method in a formatted way, pretty method can be added.                                                                                                                                                                                  |
##### mongosh UPDATING data commands
| command                                                | action                                                                                                                                                                                                       |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `db.collection.updateOne({filter}, {$set: {fields}})`  | Finds the first occurrence of `filter` and <br>updates it with the contents of the <br>contents of `fields` object. If the <br>document does not have this field, it<br>will be created and the value added. |
| `db.collection.updateMany({filter}, {$set: {fields}})` | Finds all occurences of `filter` and<br>updates them with the contents of the<br>`fields` object. Any of the resulting <br>documents that do now have any of the<br>update fields will have them added.      |
##### mongosh DELETING data commands
| command                              | action                                                                                                                                                             |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `db.collection.deleteOne({filter})`  | Finds the first occurrence of `filter` and deletes it from the <br>collection. If no filter is provided, the first document of the <br>collection will be deleted. |
| `db.collection.deleteMany({filter})` | Finds all occurrences of `filter` and deletes them from the<br>collection. If no filter is provided, all documents will be <br>deleted from the collection.        |