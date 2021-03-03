### Spacing

In almost every case, `padding` and `margin` properties are defined using the *spacing scale* within the site [Theme]() and is set for each breakpoint (also defined in the Theme file).

This approach relies on the use of [Grid Styled](https://github.com/jxnblk/grid-styled) - specifically, the "Spacing Scale" part of the [Theming section](https://github.com/jxnblk/grid-styled#theming).

The spacing scale we use is based on Grid Style's which is actually an implementation of the [8pt grid system](https://spec.fm/specifics/8-pt-grid). The specific values from `theme.js` are as follows:

```js
const spacing = [
  0,
  4,
  8,
  16,
  24,
  32,
  48,
  64,
  96,
  128,
  192,
  256
]
```

For example, if you want to set the `margin-bottom` property to `24px` at the first and second breakpoint, and `48px` for the third, on a `<Box>` component, you would simply write the following:

```jsx
<Box mb={[ 4, 4, 6 ]}>
```

There's a [full list of the props](https://github.com/jxnblk/grid-styled#props) for the `<Box>` component.

There are also Sass variables that mirror these in the `_variables.scss` file and can be used throughout the scss files like so:

```scss
.class {
  margin-bottom: space(4)

  @include breakpoint('large') {
    margin-bottom: space(6);
  }
}
```

In Sass, to set the value to zero using this approach, just write out `0` without the `space` function as Sass lists can't be read like arrays (starting at zero) so the spacing value starts at 4. This way, the values line up and you don't need to use two different numbers to get the same value.
