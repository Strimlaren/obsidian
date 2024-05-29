Back to [[FJSx23]] / [[React]]
### What is it?
Props (short for properties) in React are used to pass data from a parent component to a child component. They are immutable and allow components to be customizable and reusable by accepting different sets of data. Props are specified as attributes in JSX and accessed within the child component as properties of the props object.

![[Screenshot_6.png]]
### Props syntax:
![[Screenshot_7.png]]
![[Screenshot_8.png]]

You can send props as dynamic data like you would expect in JavaScript, like so:
```JSX
import { CORE_CONCEPTS } from "./assets/data/";

<CoreConcept 
	title={CORE_CONCEPTS[0].title}
	description={CORE_CONCEPTS[0].description}
	image={CORE_CONCEPTS[0].image}
/> 
```
**NOTE:** When importing named imports, curly braces `{}` must be used in the import. Default imports use the default function name without curly braces.

You can also use the spread operator to send all props at once if they are already inside an object with this shorter syntax, but beware of prop key-names, if they are defined as for example `title="my webpage"` inside the CORE_CONCEPTS array, then the component CoreConcept will have to use that key to reach it, for example `props.title`.
```JSX
import { CORE_CONCEPTS } from "./assets/data/";

<CoreConcept {...CORE_CONCEPTS[0]} /> 
```

##### Receiving Props inside Components

The standard way of receiving props. Any amount of props will be received and turned into an object called in this case "props", and the values inside tapped into with usual JS object dot notation:
```JSX
export default function CoreConcept(props) {
	return <h2>{props.title}</h2>
}
```

With JS object destructuring:
```JSX
export default function CoreConcept({title}) {
	return <h2>{title}</h2>
}
```

```JSX
export default function CoreConcept(props) {
	return <h2>{props.title}</h2>
}
```

