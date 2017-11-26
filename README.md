# babel-plugin-tailwind

Transforms [TailwindCSS](https://www.tailwindcss.com) classes to CSS-in-JS at build time.

> Note - Works with CSS-in-JS libraries that accept a style object such as Glamor, Glamorous, CXS, etc...

Before:

```jsx
import { css } from "glamor";

const classes = css(tw("w-5/6 sm:text-purple md:text-red md:border-purple"));

class App extends React.Component {
  render() {
    return <div className={classes}>what now</div>;
  }
}
```

After:

```jsx
import { css } from "glamor";

const classes = css({
  width: "83.33333%",
  "@media (min-width: 576px)": {
    color: "#9561e2"
  },
  "@media (min-width: 768px)": {
    color: "#e3342f",
    borderColor: "#9561e2"
  }
});

class App extends React.Component {
  render() {
    return <div className={classes}>what now</div>;
  }
}
```

## Installation

Assuming you already have babel setup in your project.

`yarn add babel-plugin-tailwind`

.babelrc

```javascript
{
  ...,
  "plugins": ["babel-plugin-tailwind"]
}
```

## Custom TailwindCSS Config

This is possible! look in the `example` folder.

```
cd example
yarn
yarn start
```

I hope to write better instructions "soon"!