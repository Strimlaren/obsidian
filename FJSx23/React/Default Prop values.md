Back to [[FJSx23]] / [[React]]
### What is it?

```JSX
export default function Button({ color, fontSize, background = "cyan" }) {
	return (
		...
	)
}

<Button color="red", fontSize={24}>Click me</button> // Button with cyan background

<Button color="red", fontSize={24} background="white">Click me</button> // White background
```