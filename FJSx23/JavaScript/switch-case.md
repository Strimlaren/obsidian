Back to [[JavaScript]]
### Switch-case
Used for choosing to do a different action depending on the value of a variable.

```javascript
let variable = Math.random(1, 6);

switch(variable) {
	case 1:
		..code;
		break;
	case 2:
	case 3:
		..code;
		break;
	case 4:
		continue;
	case 5:
		console.log("You win!");
	default:
		console.log("You did something wrong.");
}
```