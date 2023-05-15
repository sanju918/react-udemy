# REACT APP

Steps to create the react app

## 1. Creating and initializing application

- in VScode terminal run the following command. `npx create-react-app <location>`

  ```shell
  npx create-react-app ./
  ```

- Delete existing `src` folder and create a new folder with `src`
- Add a file `index.js` in `src` folder with the following content

  ```javascript
  <!-- index.js -->

  import React from "react";
  import ReactDOM from "react-dom";

  import './index.css';
  import App from "./App";

  ReactDOM.render(<App />, document.getElementById("root"));
  ```

- Create a file `App.js`. Use `rafce` shortcut to add the initial lines of code to this file.

```javascript
// App.js

import React from "react";
import "./App.css";

const App = () => {
  return <div>App</div>;
};

export default App;
```

## 2. To Install the dependencies

- Update the file `package.json` with required dependencies
- run `npm install --legacy-peer-deps`

## 3. Create an `index.css` file under folder `src`

```css
/* index.css */

@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700&display=swap");

body {
  margin: 0;
  padding: 0;
  font-family: "Open Sans", sans-serif;
}

@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 4. Create a file `App.css` under `src` folder.

```css
/* App.css */

@import url("https://cdn.syncfusion.com/ej2/material.css");

.sidebar {
  box-shadow: rgb(113 122 131 / 11%) 0px 7px 30px 0px;
}
.nav-item,
.navbar {
  z-index: 10000;
}
@media screen and (max-width: 800px) {
  .sidebar {
    z-index: 10000000;
  }
}

.e-dlg-center-center,
.e-quick-popup-wrapper.e-device {
  z-index: 1000000 !important;
}

::-webkit-scrollbar {
  width: 6px;
}
::-webkit-scrollbar-thumb {
  background-color: rgb(216, 216, 216);
  border-radius: 40px;
}
::-webkit-scrollbar-track {
  background-color: transparent;
}

/* color-picker style  */

#preview {
  background: transparent
    url("https://ej2.syncfusion.com/react/demos/src/color-picker/images/pen.png")
    no-repeat;
  display: inline-block;
  height: 80px;
  margin: 10px 0;
  min-width: 300px;
  max-width: 600px;
  background-color: #008000;
}

.e-input-group:not(.e-float-icon-left),
.e-input-group.e-success:not(.e-float-icon-left),
.e-input-group.e-warning:not(.e-float-icon-left),
.e-input-group.e-error:not(.e-float-icon-left),
.e-input-group.e-control-wrapper:not(.e-float-icon-left),
.e-input-group.e-control-wrapper.e-success:not(.e-float-icon-left),
.e-input-group.e-control-wrapper.e-warning:not(.e-float-icon-left),
.e-input-group.e-control-wrapper.e-error:not(.e-float-icon-left) {
  border: none;
}
```

## 5. Install `tailwind`

Follow the process in tailwind website to install tailwind. Since most of the files are included in the package.json and already installed, we can directly create the settings file.

- In the root directory of the project create a file `tailwind.config.js`

```javascript
// tailwind.config.js

module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  darkMode: "class",
  theme: {
    fontFamily: {
      display: ["Open Sans", "sans-serif"],
      body: ["Open Sans", "sans-serif"],
    },
    extend: {
      fontSize: {
        14: "14px",
      },
      backgroundColor: {
        "main-bg": "#FAFBFB",
        "main-dark-bg": "#20232A",
        "secondary-dark-bg": "#33373E",
        "light-gray": "#F7F7F7",
        "half-transparent": "rgba(0, 0, 0, 0.5)",
      },
      borderWidth: {
        1: "1px",
      },
      borderColor: {
        color: "rgba(0, 0, 0, 0.1)",
      },
      width: {
        400: "400px",
        760: "760px",
        780: "780px",
        800: "800px",
        1000: "1000px",
        1200: "1200px",
        1400: "1400px",
      },
      height: {
        80: "80px",
      },
      minHeight: {
        590: "590px",
      },
      backgroundImage: {
        "hero-pattern": "url('https://i.ibb.co/MkvLDfb/Rectangle-4389.png')",
      },
    },
  },
  plugins: [],
};
```

- Create another file in the root directory named `craco.config.js`

```javascript
// craco.config.js

module.exports = {
  style: {
    postcss: {
      plugins: [require("tailwindcss"), require("autoprefixer")],
    },
  },
};
```

## Finally - Run react

Run the commmand `npm start` to run the application. It will run the application in localhost:3000.
