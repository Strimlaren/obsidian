Back to [[FJSx23]] / [[React]]
### Props are not forwarded automatically
Props that are named the same way as standard html attributes will NOT automatically be forwarded and set to the correct tags inside receiving components. React cannot know what those props are for or where exactly they are meant to be forwarded. For example sending an "id" to a component that has an HTML structure with several tags, it cannot possibly or reasonably know where to put it.

![[Screenshot_17.png]]

##### Proxy-props (forwarded props)
Good when creating wrapper components. With the `...props` way of assigning attributes inside an element inside JSX, all remaining props coming in to the component function will be assigned there. The desctructured `...props` will clump all remaining props inside an object, while the `...props` inside the section html tag will spread out the content of the props prop object and set them as individual attributes inside section.

```JSX
return ( 
	<div>
		<Section title="New Section" id="example" className="active"/>
	</div>
)


export default function Section({ title, children, ...props}) {
	return (
		<section {...props}>
			<h2>{title}</h2>
			{children}
		</section>
	)
}
```

##### Why do this?
Syntactical sugar, save time writing the same code and use less space. Imagine sending several or many props to a component the likes of `<MyButton isSelected={selectedTopic === "state"} onClick={() => handleSelect("state")}`. Receiving them with a simple `...props` and spreaing them to the correct HTML element with an equally simple `...props` results in well.. I imagine its self-explanatory at this point.