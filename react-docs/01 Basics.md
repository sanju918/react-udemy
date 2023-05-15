# Basics

## Converting HTML into JSX

- All prop names follow `camelCase`, Example: `onFoucus`

  | HTML                      | Equivalent JSX            |
  | ------------------------- | ------------------------- |
  | `<input maxlenght="5" />` | `<input maxLength={5} />` |
  | `<form autocapitalize />` | `<form autoCapitalize />` |
  | `<form novalidate />`     | `<form noValidate />`     |

- Number attributes use curl braces `{}`,

  | HTML                      | Equivalent JSX            |
  | ------------------------- | ------------------------- |
  | `<input maxlenght="5" />` | `<input maxLength={5} />` |
  | `<meter optimum="50" />`  | `<form optimum={50} />`   |

- Boolean `true` can be written with just the property name and `false` with empty curl braces

  | HTML                           | Equivalent JSX                 |
  | ------------------------------ | ------------------------------ |
  | `<input spellcheck="true" />`  | `<input spellCheck />`         |
  | `<input spellcheck="false" />` | `<input spellCheck={false} />` |

- The `class` attribute is written as `className`

  | HTML                   | Equivalent JSX             |
  | ---------------------- | -------------------------- |
  | `<div class="main" />` | `<div className="main" />` |
  | `<li class="item" />`  | `<li className="item" />`  |

- In-line style attributes are provided as objects, Example: `<input type="number" min={5} max={10} style={{ border: "2px solid red" }} />`

  | HTML                                                     | Equivalent JSX                                             |
  | -------------------------------------------------------- | ---------------------------------------------------------- |
  | `<input style="border: 2px solid red;" />`               | `<input style={{ border: '2px solid red' }} />`            |
  | `<a style="text-decoration: 'none'; padding: '5px';" />` | `<a style={{ textDecoration: 'none', padding: '5px' }} />` |

## `import` and `export` in React

There are two types of exports `default` and `named`.

### `default` export

- There can be only one default export exist in a file
- The name of the default export can be changed while importing
- The benefit of changing the name of the componenet while importing is to avoid if any other component or variable declared in the file which might raise confusion.

Example:

```javascript
// index.js

// 1. import the React and ReactDOM libraries
import { React } from "react";
import { createRoot } from "react-dom/client";
import App from "./App";

// 2. Get a reference to the div with ID root
const el = document.getElementById("root");

// 3. Tell react to take control of that element
const root = createRoot(el);

// 5. Show the component on the screen
root.render(<App />);
```

```javascript
// App.js

function App() {
  return <h1>Hi There</h1>;
}

export default App;
```

### `named` export

- Use when exporting multiple variables
- Can have multiple named exports
- Two ways to write the named exports

  Way - 1

  ```javascript
  // App.js

  function App() {
    return <h1>Hi There</h1>;
  }

  export default App;

  const messsage = "hi";
  export { message };
  ```

  Way - 2

  ```javascript
  // App.js

  export default function App() {
    return <h1>Hi There</h1>;
  }

  export const message = "hi";
  ```

### `named` import

- Use curly baraces `{message}` while importing named exports
- Single import statement can get both default `named` and `default` export.
- Named exports can not be renamed.

```javascript
// index.js

import App, { message } from "./App";
```

```javascript
// App.js

export default function App() {
  return <h1>Hi There</h1>;
}

const message = "hi";
export { message };
```

## Importing Modules/Packages VS user defined files

- `./` or `../` is used while importing a user defined file
- No `./` or `../` means it's importing a package

```javascript
// index.js

// importing package
import { React } from "react";
import { createRoot } from "react-dom/client";

// Importing user defined file
import App from "./App";
import { message } from "./App";
```
