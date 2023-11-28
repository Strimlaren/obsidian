Back to [[CSS]]

### What is it?
A pattern of elements and other terms that tell the browser which HTML elements should be selected to have the CSS property values inside the rule applied to them.

### Universal Selector

```css
* {

}
```
### Element Selector

```css
h1 {

}
```
### Class Selector

```css
.my-class {

}
```
### ID Selector

```css
#my-id {

}
```
### Pseudo Selector

```css
h1:hover {

}
```

### Combinators

#### Descendant Selector
All elements that are some kind of descendant of the first element will be selected.
```css
h1 p {

}
```

#### Adjacent Siblings Combinator
Adjacent sibling will select the element that directly follow the first element.
```css
h2 + p {

}
```
#### General Sibling
General sibling will select the element that follow the first element but does not have to be directly after it.
```css
h2 ~ p {

}
```

#### Child Selector
Will select an element that is a direct child of the first element.
```css
div > p {

}
```
