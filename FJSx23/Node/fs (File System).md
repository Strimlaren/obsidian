Back to [[FJSx23]] / [[Node.js]]
### What is it?
The `fs` module provides an API for interacting with the file system in a manner closely modeled around standard POSIX functions. It allows you to work with the file system on your computer, enabling operations such as reading, writing, updating, and deleting files.

##### .readFileSync( ) & .readFile( )
Used for reading from files synchronously/asynchronously.
##### .writeFileSync( ) & .writeFile( )
Used for writing to files synchronously/asynchronously.
##### .appendFileSync( ) & .appendFile( )
Used for appending content synchronously/asynchronously to files.
##### .unlinkSync( ) & unlink( )
Used for deleting files synchronously/asynchronously.

```JavaScript
const fs = require('fs');

// Asynchronous read
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Asynchronous read:', data);

  // Asynchronous write
  fs.writeFile('example.txt', 'Some content to write into the file', err => {
    if (err) {
      console.error(err);
      return;
    }
    console.log('File has been written asynchronously');

    // Asynchronous append
    fs.appendFile('example.txt', '\nSome content to append', err => {
      if (err) {
        console.error(err);
        return;
      }
      console.log('Content has been appended asynchronously');

      // Asynchronous delete
      fs.unlink('example.txt', err => {
        if (err) {
          console.error(err);
          return;
        }
        console.log('File has been deleted asynchronously');
      });
    });
  });
});

// Synchronous read
const dataSync = fs.readFileSync('example.txt', 'utf8');
console.log('Synchronous read:', dataSync);

// Synchronous write
fs.writeFileSync('example.txt', 'Some content to write into the file');
console.log('File has been written synchronously');

// Synchronous append
fs.appendFileSync('example.txt', '\nSome content to append');
console.log('Content has been appended synchronously');

// Synchronous delete
fs.unlinkSync('example.txt');
console.log('File has been deleted synchronously');

```