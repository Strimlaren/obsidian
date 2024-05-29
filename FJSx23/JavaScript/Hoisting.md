Back to [[JavaScript]] / [Functions](Functions.md)

### Hoisting

```javascript
my_name = "Anders";

say_hello(my_name);

function say_hello(name) {
console.log(`Hello ${name}!`);
}
```

Even though the function is called before it is declared in this example, the code will still run correctly thanks to hoisting. Hoisting will make sure that functions will, when the script is run, moved to the top of the document and read first, so that all code that possibly calls the function will always have it available when it is run.

**NOTE** [[Arrow Functions]] are NOT hoisted. Use caution with arrow functions as it is important to have them in correct places in the flow to avoid "is not a function" errors.