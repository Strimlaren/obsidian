Back to [[JavaScript]]
### Strict mode
Invoking strict mode in vanilla JS is done by writing it on the topmost line of any document, before any other non-comment code.
```javascript
"use strict";

...code
```

##### Running strict vs non-strict:
1. Eliminates some JavaScript silent errors by changing them to throw errors.
2. Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
3. Prohibits some syntax likely to be defined in future versions of ECMAScript.