# Project Structure

```shell
src
| - index.js
| - App.js
| - components
    | - searchBar.js
    | - ImageShow.js
    | - ImageList.js
```

## API Usage

App --> API CAll --> Unsplash API

- React has no tools, objects, functions for making HTTP requests
- React only cares about showing content and handling user events
- This is kind of good! We can write a lot of business logic + data fetching without worrying about React!
- To make reqeusts, we commonly use either `Axios` or `Fetch`
- `Axios` is easier to start with
- Install `Axios`

  ```shell
  npm install axios
  ```

## Flow of API Call in JavaScript

In JS, when there is an HTTP request to fetch some data, by default JS will not wait for the response before going to next line of code. Hence to make execution faster, it will immediately switches to next line of code without waiting for the response. In such cases we need to tell JS to wait for response.

- JS starts the request...
- Tell JS to wait for a response
- Tell JS to show the response once it is recevied.

## Syntax of `Axios` API call

```javascript
axios.get(url, {
  headers: {},
  params: {},
});
```

- `axios.get`: Request method. Can be 'get', 'post', 'del', etc.
- `(url, {})`: URL is where we want to make the request to
- `headers: {}`: Headers that we want to add into the request.
- `params: {}`: Key-Value pairs that will be turned into a query string and added to the URL

## Example of `Axios`

```javascript
// api.js

import axios from "axios";

const searchImages = async () => {
  const response = await axios.get("https://api.unsplash.com/search/photos", {
    headers: {
      Authorization: "Client-ID HI6iaiHnxmNdJVp1zODWtMe_jydDH13N3k6fjLASFTA",
    },

    params: {
      query: "cars",
    },
  });
  console.log(response);
  return response;
};

export default searchImages;
```
