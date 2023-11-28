Part of [[CSS]]
### What is it?
Border-box and content-box are both values to the CSS attribute `box-sizing`. 

```css
box-sizing: content-box;
```

**content-box:** This is the default value of box-sizing. The dimension of element only includes ‘height’ and ‘width’ and does not include ‘border’ and ‘padding’ given to element. Padding and Border take space outside the element.

```css
box-sizing: border-box;
```

**border-box:** In this value, not only width and height properties are included but you will find padding and border inside of the box for example .box {width: 200px; border: 10px solid black;} renders a box that is 200px wide.

### Summary:
`content-box` will grow in size when padding and border grows. Padding and border does not count into the size of the content. It guarantees its content the given width to work with.
`border-box` will stay the same size while the size of content decreases as the padding and border grows. It guarantees the given width will not change if padding and border changes.

So the `border-box` will always stay the same size and will force its content to adapt as the border and padding grows larger, as they will automatically be counted toward its given size.

![](https://i.gyazo.com/b7496db428fa3b209b0f45871290fada.png)