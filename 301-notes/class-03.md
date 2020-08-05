## Responsive Web Design FROM (https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)
Responsive - change due to viewport
Adaptive - built for a group of preset factors
Mobile sites- light and for mobile devices 

Flexible Layouts use Relative Viewport Lengths (vw, vh, vmin, vmax). They don't use pixes, etc. `Formula: result = target / context`.

Formula Example (From site)

```html
<h1>100% Wide Container</h1>

<div class="container">
  <section>Section</section>
  <aside>Aside</aside>
</div>

<h1>75% Wide Container</h1>

<div class="container container-75">
  <section>Section</section>
  <aside>Aside</aside>
</div>

<h1>50% Wide Container</h1>

<div class="container container-50">
  <section>Section</section>
  <aside>Aside</aside>
</div>
```

```css 
section,
aside {
  margin: 1.858736059%; /*  10px ÷ 538px = .018587361 */
}
section {
  float: left;
  width: 63.197026%;    /* 340px ÷ 538px = .63197026 */   
}
aside {
  float: right;
  width: 29.3680297%;  /* 158px ÷ 538px = .293680297 */
}

```

Flexible layout: min-width, max-width, min-height, max-height

**Media Queries**
Useful for when the viewport is very small. Can specify type all, screen, print, tv, braille, etc. Default is screen.

```css
/* examples from site */
/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}

@media all and (min-width: 800px) and (max-width: 1024px) {...}

/* Black and white or monochrome screens  */
@media not screen and (color) {...}

/* default is all. */

/* Landscape vs Portrait */
@media all and (orientation: landscape) {...}

/* Aspect and pixel ratio media queries */

```

Example of Media query with max width of 420. Floats are removed at 420px.

```css
/* from site */
@media all and (max-width: 420px) {
  section, aside {
    float: none;
    width: auto;
  }
}
```

Breakpoints: Should be introduced only when website starts to break or look weird. 

Mobile first approach: Start with smaller viewport and use media queries to add styles as the viewport increases.

Initial-scale: between 1 and 10. Leave scale option on. Used for accessibility. 

Viewport Rule: 

```css
/* viewport example from site */
@viewport {
  width: device-width;
  zoom: 1;
}
```

## All About Floats FROM (https://css-tricks.com/all-about-floats/)
Float left or right, used so text can flow around the element. 
Can also be used for entire site. 

`clear` a float: Used to move the element under the other floated items.

```css
/* Moves the footer under both the main content (float left) and the side bar (float right) */
#footer {
  clear: both;			
}
```

Beware of the "collapsed" parent element if only floats are the children. 

**Clearing Floats**: 
    - The Empty Div Method: add an empty div
    - The Overflow Method: set css overflow to visibility hidden on parent element.
    - The Easy Clearing Method

**Floats are fragile**
- Pushdown: floated item is wider than the float itself (usually imgs). Browsers render it outside. 
- Double Margin Bug: FIX: `display: inline`
- 3px Jog: Text is pushed away around the float. FIX: set width or height on text.
- Bottom Margin Bug: Bottom margin of children elements is ignored by parent. FIX: Use bottom padding on the parent.

## Don't Overthink It Grids FROM (https://css-tricks.com/dont-overthink-it-grids/)
Many sites use grid. 

- Wrapper div for grid set to width: auto. 
- Columns can be floated. Can set class names to ".col-1-2" etc. And set those to width: %.
- Clear
- Gutters can be tricky. Use box-sizing: border-box so width is not impacted by padding and borders.

## Floats Explained FROM (https://www.freecodecamp.org/news/css-floats-explained-by-riding-an-escalator-57fa55232333/)
Floats create alternate flows: normal, left, right. 
Floats create new relationships between flows. 

`Clear: left` align behind the first element that is floated left. 
`clear: both` escalator example, person takes up both sides of the escalator because there is a suitcase. 