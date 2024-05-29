Back to [[FJSx23]] / [[React]]
### What is it?
When changing a state, a common best practice is to always pass a callback function with a parameter in the setState function that brings in the current state, passes it in and then letting that function change the state. This is to make sure that it is always the current state per this line of code that is being changed. Else React will assume the same state when for example a handle function is called, and setState is called multiple times inside it. Instead of incrementing 1 to a number 3 times, it will add 1 to that original state number 3 times and you will end up as if you did only one incrementation.

```JSX
const [increment, setIncrement] = useState(1);

function handleIncrement() {
	setIncrement(increment + 1); // increment = 2
	setIncrement(increment + 1); // increment = 2
	setIncrement(increment + 1); // increment = 2
}
```

```JSX
const [increment, setIncrement] = useState(1);

function handleIncrement() {
	setIncrement((increment) => increment + 1); // increment = 2
	setIncrement((increment) => increment + 1); // increment = 3
	setIncrement((increment) => increment + 1); // increment = 4
}
```