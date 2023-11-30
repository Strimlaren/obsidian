Back to [[JavaScript]]
### Looping through objects with for in
Used for looping through objects.

```javascript
const fruits = {
	banana: "yellow",
	kiwi: "green",
	apple: "red"
}

for (let fruit in fruits) {
	console.log(fruit); //Iterate keys
	console.log(fruits[fruit]) //Iterate values
}
```