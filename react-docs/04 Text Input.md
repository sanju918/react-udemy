# Handling Text Input in JavaScript

1. Create a new piece of state
2. Create an handler to watch for the `onChange` event
3. When the `onChange` event fires, get the value from the input.
4. Take that value from the input and use it to update your state.
5. Pass your state to the input as the value prop

## Example

```javascript
import React from "react";

// Udemy's code editor is a little weird... We do *not* need an 'import {useState}' line

function App() {
  // 1. a piece of state
  const [term, setTerm] = useState("");

  // 2. event handler to watch for the onChange event
  const handleChange = (event) => {
    // 3. When the onChange event fires, get the value from the input by referencing event.target.value and 4. update the state

    setTerm(event.target.value);
  };
  return (
    <div>
      <div>Enter some text</div>
      <input onChange={handleChange} />
      <h3>Your Text</h3>
      // 5. Pass your state to the input as the value prop
      <p>{term}</p>
    </div>
  );
}

const useState = React.useState;
export default App;
```
