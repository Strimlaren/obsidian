Back to [[JavaScript]]
### What is it?
Object in arrays are an array variant holding data with key-value pair methodology, removing the need to know an items index to be able to fetch it. They are easily recognized by the curly braces. To iterate through objects, the [for..in loops](for...in) are used.

```javascript
const my_object = {key1: "value1", 
				   key2: false,
				   key3: ["one", "two"],
				   key4: {fruit: "apple"},
				   key5: 99
				   }
				   
// Calling the Object items with dot notation
my_object.key5; // 99
my_object.key4.fruit; // "apple"
my_object.key3[1]; // "two"

// Calling the object items with bracket notation
my_object["key5"]; // 99

//Creating new key-value pairs in an object
my_object.key10 = "Family Guy";
```

