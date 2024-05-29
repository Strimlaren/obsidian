Back to [[FJSx23]] / [[React]]
### What is it?
A hook for more complex state management. Works a little differently from useState, and collects many or all states on one place, and has useContext functionality built in.

```jsx
import { useState, useReducer } from "react";

// useReducer function with all actions available for all states that are provided by this reducer.
const reducer = (state, action) => {   
	switch (action.type) {
	  case "increment":
	    return { count: state.count + 1};
	  case "decrement":
	    return { count: state.count - 1};
	  case "newUserInput":
	    return { userInput: action.payload };
	  case "toggleColor":
	    return { color: !state.color };
	  default:
	    throw new Error();
	}
}

function App() {
const [userInput, setUserInput] = useState(""); // useState
const [count, setCount] = useState(0);          // useState
const [color, setColor] = useState(false);      // useState

cosnt [state, dispatch] = useReducer(reducer, { count: 0, userInput: "", color: false });  // useReducer

return (
    <main className="App" style={{ color: color ? "#FFF" : "#FFF952" }}> // useState
    <main className="App" style={{ color: state.color ? "#FFF" : "#FFF952" }}> // useReducer
      <input
        type="text"
        value={userInput} // useState
        value={state.userInput} // useReducer
        onChange={(e) => setUserInput(e.target.value)} // useState
        onChange={dispatch({ type: "newUserInput", payload: e.target.value })} // useReduer
      />
      <br />
      <br />
      <p>{count}</p>   // useState
      <p>{state.count} // useReducer
      <section>
        <button onClick={() => setCount((prev) => prev - 1)}>-</button>  // useState
        <button onClick={() => setCount((prev) => prev + 1)}>+</button>  // useState
        <button onClick={() => setColor((prev) => !prev)}>Color</button> // useState
        
        <button onClick={dispatch({ type: "decrement" })}>-</button> // useReducer
        <button onClick={dispatch({ type: "increment" })}>+</button> // useReducer
        <button onClick={dispatch({ type: "toggleColor" })}>Color</button> // useReducer
      </section>
      <br />
      <br />
      <p>{userInput}</p>
    </main>
  );
}
```