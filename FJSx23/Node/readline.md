Back to [[FJSx23]] / [[Node.js]]
### What is it?
The `readline` module provides an interface for reading data from a readable stream (such as `process.stdin`) one line at a time. It's a part of Node.js's standard library and does not require any additional installation.

##### .createInterface( )
The `createInterface` method is part of the `readline` module. It creates an interface for reading data from a readable stream (like `process.stdin`) and writing data to a writable stream (like `process.stdout`).

##### process.stdin & process.stdout
- **`process.stdin`**: A readable stream for the standard input (usually the keyboard input).
- **`process.stdout`**: A writable stream for the standard output (usually the console).

These are part of the `process` global object in Node.js, which provides information about and control over the current Node.js process.

#### Example:
```Node.js
const readline = require('readline'); 

const rl = readline.createInterface({ 
	input: process.stdin, 
	output: process.stdout 
}); 

rl.question('What is your name? ', (answer) => { 
	console.log(`Hello, ${answer}!`); 
	rl.close(); 
}); 

rl.on('close', () => { 
	console.log('Interface closed.'); 
	process.exit(0); 
});
```