Back to [[CSS]]

### What is it?
If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element. Think of specificity as a score/rank that determines which style declaration is ultimately applied to an element.

### Specificity hierarchy

`<a href="" style="color: red">` > `#id-name` > `.class, a:hover` > `div`

![](https://i.gyazo.com/3017025b0153d51172ad8bdfc13ffcd1.png)

### Specificity calculation

- If the element has inline styling, that automatically1 wins (1,0,0,0 points)
- For each ID value, apply 0,1,0,0 points
- For each class value (or pseudo-class or attribute selector), apply 0,0,1,0 points
- For each element reference, apply 0,0,0,1 point

You can generally read the values as if they were just a number, like 1,0,0,0 is “1000”, and so clearly wins over a specificity of 0,1,0,0 or “100”. The commas are there to remind us that this isn’t really a “base 10” system, in that you could technically have a specificity value of like 0,1,13,4 – and that “13” doesn’t spill over like a base 10 system would.

![](https://i.gyazo.com/50dedc7f00d0603e6d4586b990c5278e.png)