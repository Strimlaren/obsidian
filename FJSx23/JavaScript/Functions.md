Back to [[JavaScript]]
### Functions
To keep up with DRY (dont repeat youself) when coding and make code readable as well as separate pieces of code in a certain way, functions can be used.
##### Function declaration:
```javascript
function calculate_average(num1, num2) {
	let average = (num1 + num2) / 2;
	return average;
}

calculate_average(1, 5);
```

Functions can take any or no parameters as in-values. When calling the function, one must pass the required arguments. The function can be set to return a value which can then be used for other things from the point where the function was called. 
##### Hoisting
Functions in JS are automatically [hoisted](Hoisting.md), which means they will be moved to the top of the document at runtime and be available for use immediately in the code, no matter where the function was declared.
##### Other types of functions
There are other types of functions like [[Arrow Functions]], [Function Expressions](Function Expression)