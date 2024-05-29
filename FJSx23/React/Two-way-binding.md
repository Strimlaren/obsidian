Back to [[FJSx23]] / [[React]]
### What is it?
two-way binding in React refers to the synchronization of data between a form input field and a component's state. This means that changes made to the input field by the user are immediately reflected in the component's state, and vice versa. It provides a seamless way to keep the UI and the component's data in sync without requiring manual event handling for input changes.

```JSX
const [playerName, setPlayerName] = useState(initialName);

funtion handleChange(event) {
	setPlayerName(event.target.value)
}

<input value={playerName} onChange={handleChange} />
```