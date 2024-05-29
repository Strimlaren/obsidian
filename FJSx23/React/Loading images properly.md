Back to [[FJSx23]] / [[React]]
### What is it?
Instead of importing images directly like traditional HTML `<img src="./img.jpg></img>` you can instead import the image into a variable and use that variable inside the source attribute.
```JSX
import reactImg from "./assets/images/this-is-an-image.jpg";

<img src={reactImg} alt="some image" />
```