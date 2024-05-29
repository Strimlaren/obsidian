Back to [[FJSx23]] / [[TypeScript]]
### What is it?
When assigning types to Typescript variables and letting them take the form of one and/or other types.

##### Unions
The much more common use case where you can tell TS that variables can accept several different types or for example say exactly what returns a function will have, even set strings or numbers, not only types.
```typescript
let name: "Mirza" | "Anders";
const age: number | string;
const myArray: number | boolean[];

function headsOrTails(): "Heads" | "Tails" {
	if (Math.random() > 0.5) return "Heads";
	return "Tails";
}
```

##### Intersections
The much less common use case where one can merge several types into one:
```typescript
interface point2d {
	pointY: number;
	pointX: number;
}

interface point3d {
	pointY: number;
	pointX: number;
	pointZ: number;
}

type point = point2d & point3d;

let p: point = {
	pointY: 10,
	pointX: 5,
	pointZ: 30
}
```