Back to [[FJSx23]] / [[Typescript]]
### What is it?
In Typescript, Type assertion is a technique that informs the compiler about the type of a variable. Type assertion is similar to typecasting but it doesn't reconstruct code. You can use type assertion to specify a value's type and tell the compiler not to deduce it.

As an example, TS will not know if an HTML element exists or what type it is. Type asserting it to a `HTMLInputElement` is guaranteeing TS that it exists and telling it what type it will be.
```typescript
const element = document.getElementById("inputfield") as HTMLInputElement;
```
Using type assertions is like overwriting TS type checking, and can lead to type errors down the line if not used with caution.