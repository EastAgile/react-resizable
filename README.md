### React-Resizable

[View the Demo](https://strml.github.io/react-resizable/examples/1.html)

A simple widget that can be resized via a handle.

You can either use the `<Resizable>` element directly, or use the much simpler `<ResizableBox>` element.

See the example and associated code in [TestLayout](/test/TestLayout.jsx) and
[ResizableBox](/lib/ResizableBox.jsx) for more details.

You can pass in theme object as supported by [React Themeable](https://github.com/markdalgleish/react-themeable)
to overwrite style for both `<Resizable>` and `<ResizableBox>` element:

```js
const theme = {
  wrapper: 'MyResizable__wrapper',   // if this is not defined, default to class "react-resizable"
  handle: 'MyResizable__handle'      // if this is not defined, default to class "react-resizable-handle"
};
...
<ResizableBox theme={ theme }/>
```

You can use default style found within [/css/styles.css](/css/styles.css) if you would like to not overwrite style.

You can pass options directly to the underlying `DraggableCore` instance by using the prop `draggableOpts`.
See the [demo](/test/TestLayout.jsx) for more on this.

### Installation

Using [npm](https://www.npmjs.com/):

    $ npm install --save react-resizable

### Usage

```js
const Resizable = require('react-resizable').Resizable; // or,
const ResizableBox = require('react-resizable').ResizableBox;

// ES6
import { Resizable, ResizableBox } from 'react-resizable';

// ...
render() {
  return (
    <ResizableBox width={200} height={200} draggableOpts={{...}}
        minConstraints={[100, 100]} maxConstraints={[300, 300]}>
      <span>Contents</span>
    </ResizableBox>
  );
}
```

### Props

These props apply to both `<Resizable>` and `<ResizableBox>`.

```js
{
  children: React.Element<any>,
  width: number,
  height: number,
  // If you change this, be sure to update your css
  handleSize: [number, number] = [10, 10],
  lockAspectRatio: boolean = false,
  axis: 'both' | 'x' | 'y' | 'none' = 'both',
  minConstraints: [number, number] = [10, 10],
  maxConstraints: [number, number] = [Infinity, Infinity],
  onResizeStop?: ?(e: SyntheticEvent, data: ResizeCallbackData) => any,
  onResizeStart?: ?(e: SyntheticEvent, data: ResizeCallbackData) => any,
  onResize?: ?(e: SyntheticEvent, data: ResizeCallbackData) => any,
  draggableOpts?: ?Object
};
```
