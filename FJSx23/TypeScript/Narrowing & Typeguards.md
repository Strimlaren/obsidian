Back to [[FJSx23]] / [[TypeScript]]
### What is it?
Narrowing and Typeguards are two concepts that go together. Narrowing is the concept of increasing type safety whils type guards are the actual code pieces that make it happen.
##### Narrowing <=> Type Guards
Narrowing is a way of programming to narrow down a variable type from less specific to more specific. This helps greatly to reduce runtime errors, makes the code more clear and easily readable, prevents use of wrong types as well as makes code bases more easily maintainable. 
```typescript
function example(value: string | number) {
	if (typeof value === "string") { // Type Guard
	return "you passed a string";
	}
	else return "you passed a number";
}
```
##### Custom Type Guards
Sometimes you will need to create your own type guards that checks for your own type definitions or other specific need that are not readily available.
```typescript
class User {
	name: string;
	age: number;
	isProgrammer: boolean;
	constructor(name, age, isProgrammer) {
		this.isProgrammer = isProgrammer;
		this.age = age;
		this.name = name;
	}
}

function isUser(value: unknown): variable is User { // Type predictor
	if(value instanceof User) return true;
	else return false;
}
```
