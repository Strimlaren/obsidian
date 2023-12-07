Back to [[FJSx23]] / [[HTML]]
### What is it?
To add unique information or identifiers to HTML elements that are also accessible with JavaScript. They are basically custom HTML attributes you can set however you like, as long as you start with the `-data` keyword.
```html
<div>
	<ul>
		<li id="one" data-first-list-item="500">Text Content</li>
		<li id="two" data-presentation-item="scissors">Text Content 2</li>
	</ul>
</div>
```
Getting this information from [JavaScript](obsidian://open?vault=FJSx23&file=Top%20DOM%20Manipulation%20Methods) would look like this:
```javascript
const listItemOne = querySelector("#one");

console.log(listItemOne.dataset.dataFirstListItem); 
// Output: 500
```
Note that JavaScript will convert the kebabcase data attribute names to camelcase inside the dataset object.
In CSS elements can be targeted by your custom data attributes like so:
```css
li[data-first-list-item="500"] {
	color: white;
	width: 50%;
}
```