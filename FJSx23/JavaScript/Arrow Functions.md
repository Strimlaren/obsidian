Back to [[JavaScript]] / [Functions](Functions.md)
### Arrow functions
The arrow functions which are mainly syntactical sugar, look a bit differently depending on how many parameters the function will have and wether or not it needs to contain more than one line of code.

As long as the arrow functions contain no more than one line of code, the contents will be explicitly returning the results of the functions, so the return keyword is omitted. However, more than one line of code till requires the return keyword to be used.
##### No parameters, one line of code:
```javascript
const my_value = () => alert("Hi!");

// Calling this function
my_value();
```

##### One parameter, one line of code:
```javascript
const my_value = my_para => alert(`Hi, ${my_para}!`);
// ...or:
const my_value = (my_para) => alert(`Hi, ${my_para}!`);

// Calling these functions
my_value("Anders");
```

##### Two or more parameters, one line of code:
```javascript
const my_value = (para1, para2) => alert(`Hi, ${para1} and ${para2}!`);

// Calling this function
my_value("Anders", "Sven");
```

##### Any number of parameters, more than one line of code:
```javascript
const my_value = () => {
	const age = 5;
	const name = "Anders";
	return `Name is ${name} and ${age} of age.`;
}

//Calling this function
my_value();
```

**NOTE:** The arrow functions biggest advantage is they refer to the `.this` keyword of the object the function is called on, which makes more sense. Regular functions `.this` keyword refers to the scope from where it was called. Most other languages the functions behave the same way that arrow functions behave in JS.