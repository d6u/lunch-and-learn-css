# Let's talk about HTML and CSS this time

![I know HTML and CSS](http://www.dailyblogtips.com/wp-content/uploads/html-css-tshirt.jpg)

_Disclaimer: depends on your gender, you may not want to meet ladies._

## In the `::before` and `::after`

> `::before` creates a pseudo-element that is the first child of the element matched. It is often used to add cosmetic content to an element by using the content property. This element is inline by default.
>
> -- [`::before` - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)

### What it looks like

```css
.container::before {
  content: '';
  display: block;
  width: 100px;
  height: 100px;
  background-color: red;
}
```

**Show devtool screenshot**

### Stylish hover effect

### Make most use of content

- Checkmark visited links

    ```
    #main-content a:visited:before {
      content: "\2713 ";
    }
    ```

- Use attributes

    ```html
    <a title="A web design community." href="http://css-tricks.com">CSS-Tricks</a>
    ```

    ```css
    a:before {
      content: attr(title) ": ";
    }
    ```

## Centering in the unknown

- [Centering in CSS: A Complete Guide](https://css-tricks.com/centering-css-complete-guide/)
- [Centering in the Unknown](https://css-tricks.com/centering-in-the-unknown/)

### Round 1: horizontal centering

```css
.centered {
  width: 100px;
  margin-left: auto;
  margin-right: auto;
}
```

### Round 2: unknown width horizontal centering

```css
.parent {
  text-align: center;
}
.centered {
  display: inline-block;
}
```

### Round 3: vertical centering

_CSS `vertical-align` is not for vertical centering, at least not designed with that in mind._

- For inline single line text: set `line-height` equal to the height of container.
- Do manual works by specifying the top padding or margin.

### Round 4: unknown height vertical centering

```css
.centered {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
}
```

### Round 5: unknown width and height horizontal and vertical centering

```css
.centered {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### Round 6: unknown width and height horizontal and vertical super-duper IE8 compatible don't know why you care centering

```css
.parent {
  text-align: center;
  white-space: nowrap;
}

/* Very cool ::before usage */
.parent:before {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
  margin-right: -0.25em; /* Adjusts for spacing */
}

.centered {
  display: inline-block;
  vertical-align: middle;
  /* Any width or height */
}
```

### Other solutions

- `<table/>` elements
- Flexbox centering (next section)

## What the Fl**box!?

- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### Issue with dynamically distributing elements inside container

- Wrap
- Spacing
- Centering
- Order and flow direction
- Sizing

### Example with navigation bar

### List of elements

### Centering

### Something will make your life easier

Not so productive

```css
.a {
  display: -webkit-box;  /* OLD - iOS 6-, Safari 3.1-6, BB7 */
  display: -ms-flexbox;  /* TWEENER - IE 10 */
  display: -webkit-flex; /* NEW - Safari 6.1+. iOS 7.1+, BB10 */
  display: flex;         /* NEW, Spec - Firefox, Chrome, Opera */
}

.b {
  -webkit-box-flex: 1;   /* OLD - iOS 6-, Safari 3.1-6 */
  width: 20%;            /* For old syntax, otherwise collapses. */
  -webkit-flex: 1;       /* Safari 6.1+. iOS 7.1+, BB10 */
  -ms-flex: 1;           /* IE 10 */
  flex: 1;               /* NEW, Spec - Firefox, Chrome, Opera */
}
```

Everybody should use [Autoprefixer](https://github.com/postcss/autoprefixer). Manually applying vendor prefixes is like uploading files to deploy production server using SSH.

_Side note: [PostCSS](https://github.com/postcss/postcss) is a great CSS transformation tool, think it's babel.js for CSS._

## Living on the grid

Take flexbox further

- [The future of layout with CSS: Grid Layouts](https://hacks.mozilla.org/2015/09/the-future-of-layout-with-css-grid-layouts/)
- [Can I use grid](http://caniuse.com/#search=grid) - Short answer "Not yet"
- Enable Grid layout in chrome - chrome://flags/#enable-experimental-web-platform-features

```css
.container {
  display: grid;
  grid-template-rows: 100px auto 100px;
  grid-template-columns: 100px auto;
  grid-template-areas:
    "header  header"
    "sidebar content"
    "footer  footer";
}

/* More creative use of grid-template-areas */
.container-2 {
  display: grid;
  grid-template-rows: repeat(5, 100px);
  grid-template-columns: repeat(5, 100px);
  grid-template-areas:
    ". . . . ."
    ". . . . ."
    ". . a . ."
    ". . . . ."
    ". . . . .";
}

.cell {
  grid-row-start: 1;
  grid-row-end: 2;
  grid-column-start: 1;
  grid-column-end: 3;
}

.cell {
  grid-area: header; /* defined in grid-template-areas */
}
```

[Example](http://codepen.io/daiweilu/pen/EKxoxz?editors=1100)

## Start variable names with `--` is not my fault

[CSS Variables](https://developers.google.com/web/updates/2016/02/css-variables-why-should-you-care?hl=en)

```css
:root {
  --main-color: #06c;
}

#foo h1 {
  color: var(--main-color);
}
```

```js
var styles = getComputedStyle(document.documentElement);
var value = String(styles.getPropertyValue('--primary-color')).trim();

// Set
document.documentElement.style.setProperty('--primary-color', 'var(--secondary-color)');
```

## I can't do math! Just use `calc()`

```css
.foo {
  width: calc(100% - 100px);
}
```

```css
.foo {
  --gap: 20;
  margin-top: calc(var(--gap) * 1px); /* niiiiice */
}
```
