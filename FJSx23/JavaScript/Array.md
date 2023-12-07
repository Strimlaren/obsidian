Back to [[JavaScript]]
### Arrays
Arrays in JS can hold any type of value, strings, numbers, booleans and even other arrays and [objects](Object).
```javascript
const random_basket = ["string", 12, ["one", "two"], false];

const random_years = new Array(1991, 2002, 1234, 2020);
// Calling array items
random_basket[3]; // false 
random_basket[2][0]; // "one"
```

### Useful methods

```javascript
const my_array = ["starcraft", "warcraft", "warframe"];

// .includes() checks the occurence of an item inside an array, returns a boolean
my_array.includes("starcraft"); // true

// .indexOf() returns the index value of a queried item
my_array.indexOf("warframe"); // 2
```