Back to [[FJSx23]] / [[JavaScript]]
### What is it?
Methods in JavaScript which are most commonly used and amongst many others will be the prominent ones that can cover the vast majority of DOM manipulation needs.
- `.getElementById()`
- `.querySelector()`
- `.createElement()`
- `.append()`
- `.textContent` `.innerHTML` `.innerText`
- `.remove()`
- `.setAttribute()`
- `.removeAttribute()`
- `.classList.add` `.classList.remove` `.classList.toggle`
##### Connecting to elements in the DOM:
```javascript
const my_element = document.getElementById("html-id");
// NOTE: id name with this method is not prefixed by a #

const my_element_2 = document.querySelector("any-css-selector");
// NOTE: with this method, selectors must be entered just like in CSS, 
// for exmaple classes are called with ".class", ids with "#id" etc.
```
##### Element creation:
```javascript
const div = docuement.createElement("div");
// NOTE: This only creates an empty element that sits inside the JS code.
// To show on the page, this element needs to be appended to the HTML.

document.body.append(div);
// Div will be appended as the last child of the body element.
```
##### Ways of text manipulation:
```javascript
const my_element = document.querySelector("#my-list-item-2");
// First connecting to an element

my_element.textContent = "Hi there. This will be the new text content";
// Will set text content inside element with invisible characters and elements intact

my_element.innerHTML = "<strong>This text will be bolded on the page itself</strong>";
// Enables to directly insert HTML code that will be interpreted correctly on the page

my_element.innerText = "This will also be text visible on the page.";
// Will set only text content inside the element.
```
A more noticeable difference between these will be more apparent when fetching content. Assuming this HTML code:
```html
<div>
	<span style="display:none" id="one">This
	should be
	invisible.
	</span>
	<span id="two">Visible</span>
</div>
```
These would be the outcomes calling for the content of the div with the different methods:
```javascript
console.log(my_element.textContent);
// Output:
"This 
should be
invisible.
Visible"
// It grabs literally all text inside, no matter the CSS settings like display.
// It also brings line-breaks and invisble characters that are not showing on the page.

console.log(my_element.innerHTML);
// Output:
"<span style="display:none" id="one">This
	should be
	invisible.
	</span>
	<span id="two">Visible</span>"
// Returns literally everything including the HTML code in a string.

console.log(my_element.innerText);
//Output:
"Visible"
// Returns only exactly what is actually shown to the user on the page.
```
##### Removing elements:
```javascript
my_element.remove();
// Assuming my_element was created or connected to before. This completely removes
// this element from the HTML. It can be added back in again later with append
```
##### Working with attributes
```html
<span title="best title">Hello</span>
```

```javascript
console.log(my_element.getAttribute("title"));
// Outputs "best title"
console.log(my_element.title);
// Most of the attributes are attributes in the element node object and can
// also be accessed with dot notation.

my_element.setAttribute("title", "even better title");
// Title attribute is now overwritten. You can set new attributes with this as well

my_element.removeAttribute("title");
// Removes the title attribute altogether
```
##### Working with datasets
Also see [data attributes](obsidian://open?vault=FJSx23&file=HTML%2FData%20Attributes)
```html
<span data-my-custom-attribute="46">Hello</span>
```

```javascript
console.log(my_element.dataset.MyCustomAttribute);
// Output: 46
// NOTE: javascript converts custom dataset names from kebab-case to camelCase
// and removes the data- prefix

// Adding datasets from JavaScript:
my_element.dataset.newDataset = "Hello";
// This will in turn be added to the element, prefixed with data- and converted
// to kebab-case: data-new-dataset="Hello"
```
##### Working with classes
```javascript
my_element.classList.add("title-red");
// adds a class to an element

my_element.classList.remove("title-red");
// removes a class from an element

my_element.classList.toggle("title.red", true);
```
##### Manipulating CSS styles
```javascript
my_element.style.backgroundColor = "red";
// Just like with dataset, CSS attributes from JS are converted to camelCase.
```