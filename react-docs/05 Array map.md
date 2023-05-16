# Arrays in ReactJS

- Use a `key` whenever we have a list of elements and usage of map
- Add the key to the top most element in the JSX e.g first div
- `Key` must be a string and numbers
- `Key` should be unique for this list
- `Key` should be consistence across the renderers.

## Array Map Example

```javascript
import "./ImageList.css";
import ImageShow from "./ImageShow";

function ImageList({ images }) {
  const renderedImages = images.map((image) => {
    return (
      // key is set to the top most JSX element
      <div key={image.id}>
        <ImageShow image={image} />
      </div>
    );
  });
  return <div className="image-list"> {renderedImages} </div>;
}

export default ImageList;
```
