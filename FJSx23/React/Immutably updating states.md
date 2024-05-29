Back to [[FJSx23]] / [[React]]
### What is it?
Immutably updating object states in React means creating a new object when modifying state rather than directly mutating the existing object. This ensures that state changes are handled in an immutable (unchangeable) manner, preserving the integrity of the original state and preventing unintended side effects. This practice is crucial for maintaining predictable component behavior and optimizing performance in React applications.

```JSX
const [fruitSalad, setFruitSalad] = useState(["Banana", "Apple", "Kiwi"]);

function handleClick() {
	const newFruitSalad = [...fruitSalad, "Pineapple"];
	return newFruitSalad;
}
```

So, instead of changing `fruitSalad` directly, we make a "copy" of it, i.e createt a new instance of it with the spread operator, and then make additions, subtractions and other changes to it before using it/returning it.