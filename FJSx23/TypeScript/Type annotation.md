Back to [[FJSx23]] / [[TypeScript]]
### What is it?
In TypeScript, we can annotate our variables, functions etc with optional syntax that forces the use of specified types. There are many ways to do so.

##### Implicit type annotation
TypeScript can with great accuracy guess what types should be set and will do so automatically in the background
```typescript
let someNumber = 23;
someNumber = "Hi" // Error ! Cant assign string to number
```

##### Explicit type annotation
More often than not, you will want to manually set your types, and there are different ways of doing so depending on the situation and need:

Basic annotation on primitive types
```typescript
let myName: string = "Mirza";
let isProgrammer: boolean = true;
let myAge: number = 37;
```

This tells TS what types to expect as in-parameters to the function. The optional `: number` after the parameters tells TS and whoever is reading the code what type this function is expected to return.
```typescript
function add (a: number, b: number): number {
	return a + b;
}
```

Defining a constant variable, the type annotation is unnecessary as it is immutable and TS will know it as simply the value of the variable
```typescript
const age = 37;
```

Inline style type annotation for a variable Person array that contains objects which are people that have some attributes.
```typescript
const Person: {
	firstName: string;
	lastName: string;
	driversLicense: boolean;
	age: number;
}[] = [
{
	firstName: "Mirza",
	lastName: "Mesinovic",
	driversLicense: true,
	age: 37
}
{
	firstName: "Davud",
	lastName: "Mesinovic",
	driversLicense: false,
	age: 2
}
]
```

##### Tuples
Tuples are a type built in to TS that essentialy are arrays with a set number of items and with static types. In this example myTuple takes three items only, and they are a number, string and boolean specifically in that order.
```typescript
const myTuple: [number, string, boolean] = [
15,
"hello world",
false
]
```