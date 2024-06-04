Back to [[FJSx23]]
##### Text Markup

|Style|Syntax|Example|Output|
|---|---|---|---|
|Bold|`** **` or `__ __`|`**Bold text**`|**Bold text**|
|Italic|`* *` or `_ _`|`*Italic text*`|_Italic text_|
|Strikethrough|`~~ ~~`|`~~Striked out text~~`|~~Striked out text~~|
|Highlight|`== ==`|`==Highlighted text==`|==Highlighted text==|
|Bold and nested italic|`** **` and `_ _`|`**Bold text and _nested italic_ text**`|**Bold text and _nested italic_ text**|
|Bold and italic|`*** ***` or `___ ___`|`***Bold and italic text***`|**_Bold and italic text_**|
##### Code Blocks
Use triple backticks, add language code after first set of backticks for correct highlighting:

```python 
def helloWorld()
	message = "Hello World"
	if (5 > 3)
		print(message)
	return
```

##### External Links
`[Link name](Link address)`
##### Images
`![Image name | Image size](Link address)`
##### Headings
```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

Here is a heading: `# Heading`, **don't do this:** `#Heading` 
##### Emphasis
```markdown
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```
##### Line Breaks
```markdown
First line with two spaces after.  
And the next line.
```
#### Lists

##### Ordered Lists
```markdown
1. First item
2. Second item
3. Third item
```
##### Unordered Lists
```markdown
- First item
- Second item
- Third item
```
##### Links
```markdown
Link with text: [link-text](https://www.google.com)
```
##### Images
```markdown
Image with alt text: ![alt-text](https://camo.githubusercontent.com/4d89cd791580bfb19080f8b0844ba7e1235aa4becc3f43dfd708a769e257d8de/68747470733a2f2f636e642d70726f642d312e73332e75732d776573742d3030342e6261636b626c617a6562322e636f6d2f6e65772d62616e6e6572342d7363616c65642d666f722d6769746875622e6a7067)

Image without alt text: ![](https://camo.githubusercontent.com/4d89cd791580bfb19080f8b0844ba7e1235aa4becc3f43dfd708a769e257d8de/68747470733a2f2f636e642d70726f642d312e73332e75732d776573742d3030342e6261636b626c617a6562322e636f6d2f6e65772d62616e6e6572342d7363616c65642d666f722d6769746875622e6a7067)
```
#### Code Blocks

##### Inline Code Block
```markdown
Inline `code` has `back-ticks around` it.
```
##### Blocks of Code
<pre>
```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```
</pre>
##### Tables
There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the raw Markdown line up prettily.

```markdown
| Heading 1 | Heading 2 | Heading 3 |
|---|---|---|
| col1 | col2 | col3 |
| col1 | col2 | col3 |
```

##### Task list
To create a task list start line with square brackets with an empty space.
Ex: [ <space> ] and add text for task.
To check the task replace the space between the bracket with "x".

```markdown
[x] Write the post
[ ] Update the website
[ ] Contact the user
```