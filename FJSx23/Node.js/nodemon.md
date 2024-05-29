Back to [[FJSx23]] / [[Node.js]]
### What is it?
Package that is used for automatically listening for changes inside an application and automaticall restarting the server, effectively applying the changes in realtime without the need for manually reseting the server.

### Installation

```javascript
npm install -g nodemon  // Installing it globally for all future projects

npm install --save-dev nodemon // Installing it as a dev dependency 
```

### Running nodemon

```javascript
npx nodemon index.js // npx runs nodemon locally
```

### package.json
Add your own short commands for the terminal like so:
```javascript
 "scripts": {
    "test": "test",
    "start": "npx nodemon index.js"
  },
```