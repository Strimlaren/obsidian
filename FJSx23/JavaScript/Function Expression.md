Back to [[JavaScript]]
### Function expression
[Functions](Function) with no name, declared and inserted into variables. They're useful hen you want to create a new function, but don't plan on calling that function again. For example, you'll commonly use anonymous function as arguments to other functions. The advantage of an anonymous function is that it does not have to be stored in a separate file This can greatly simplify programs, as often calculations are very simple and the use of anonymous functions reduces the number of code files necessary for a program.

```javascript
const juice = function (fruit1, fruit2) {
	return `Juice with ${fruit1} and ${fruit2} was made.`;
}

juice("apples", "oranges");
```

