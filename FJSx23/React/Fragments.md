Back to [[FJSx23]] / [[React]]
### What is it?
In React, one must always return only one element, as return statements overall can only return one value at a time, returning siblings does not work. Therefore, one must always wrap siblings in a parent tag before returning it, alternatively use fragment tags, which are empty wrappers that dont result in any actual tags in the resulting html code:

```JSX
return (
	<> // Opening fragment tag
		<Header />
		<main>
			...
		</main
	</> // Closing fragment tag
);
```