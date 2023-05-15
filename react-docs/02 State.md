# React State

- Data that changes as the user interacts with our app
- When this data changes, React will update content on the screen automatically
- This is the one-and-one way we can change what content React shows. All other libraries that apper to update content use the state system behind the scenes

- Synatax:

```javascript
// App.js

import AnimalShow from "./AnimalShow";

// 1. Import the state library
import { useState } from "react";

function App() {
  // 2. Create a variable to use state
  // useState(0) This defines a piece of state with the function useState()
  // 0 is the default, starting value for our piece of state
  var [numberOfAnimals, setNumberOfAnimals] = useState(0);

  const handleClick = () => {
    console.log("Button was clicked!");

    // 3. Use the created variable to update the new value
    setNumberOfAnimals(numberOfAnimals + 1);
  };

  return (
    <div>
      <button onClick={handleClick}>Add Animal</button>
      // now the updated value can be passed on to rerender the output on the screen
      <AnimalShow count={numberOfAnimals} />
    </div>
  );
}

export default App;
```

```javascript
// the syntax
const [count, setCount] = useState(0);

// count is the state
// setCount is the setter function used to update state
// useState(0) is the state function with initial state of 0
```

## Only things to understand

1. Use the state system when you want to update content on the screen
2. Calling `useState` defines a new piece of state
3. The first argument to `useState` is used as the initial value
4. Updating state is done only using the setter function
5. Calling the setter function causes React to rerender the component
