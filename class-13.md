# EASILY CREATE STUNNING ANIMATED CHARTS WITH CHART.JS
#### https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/
Chart JS is used for creating animated charts.
From site: How to use it
Set up: Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script. It should look like this. 

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <title>Chart.js demo</title>
        <script src='Chart.min.js'></script>
    </head>
    <body>
    </body>
</html>
```

Be sure to have a `<canvas>` in HTML doc.

Can do pie, bar, and line chart. 


# Chart.js
#### https://www.chartjs.org/docs/latest/ 
Installed - OK
To render chart, need `<script>` and a `<canvas>` element.

# Basic usage of canvas
#### https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage
`<canvas>` element should look like this. 

```html
<canvas id="tutorial" width="150" height="150"></canvas>
```

Note: There is no src or alt attributes. If no width or height is specified, default measurements will be 300 pixels wide and 150 pixels high.Can add fallback content inside the canvas tags incase the browser does not support canvas.

Canvas is initially blank. Needs script to render context and draw on it. Get the node using getElementById, then getContext(). For 2D graphics, use "2d" like so.

```js
var canvas = document.getElementById('tutorial');
var ctx = canvas.getContext('2d');
```

Backup option if it's not available. 

```js
var canvas = document.getElementById('tutorial');

if (canvas.getContext) {
  var ctx = canvas.getContext('2d');
  // drawing code here
} else {
  // canvas-unsupported code here
}
```

# Drawing Shapes with Canvas 
#### https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes
Drawing with Canvas: one unit on the grid is usually 1px.
Canvas only supports 1) rectangles, 2) paths (list of points connected by lines).
    - Using Canvas options, you can draw triangles, hearts, circles, squares, etc.

Drawing a rectangle example
    - filled rectangle `fillRect(x, y, width, height)`
    - rectangle outline `strokeRect(x, y, width, height)`
    - clear transparent rectangle area `clearRect(x, y, width, height)`

Path methods: There are various drawing paths
    - `beginPath()`
    - `closePath()`
    - `stroke()` 
    - `fill()`
    - `moveTo()`
    - `lineTo()`
    - etc.

Side ways triangle example from site 

```js
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

# Applying Styles and Colors
#### https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors
colors, line styles, gradients, patterns, and shadows!

**COLORS**
Can `fillStyle = color` and color can be a name, RBG(A), or HEX values.
Can set a `ctx.globalAlpha = 0.2` which means all the shapes after this is set will have that transparency value. 

**LINES**
Can control line properties like `lineWidth = value` and `getLineDash()`. Line width default is 1.0 units. Can use for loops when drawing. This is useful for moving the pen around the pixels (which would be [i]). Line cap are the end points of the line. Can make zigzag lines.

**Line cap**
- butt - squares off the endpoints
- round - rounds the end points
- square - squares the end points

**GRADIENTS** 
Can create linear and radial gradients. Can create patterns too by repeating a design or img.

**SHADOWS** 
Can use shadows to add shadow to text too!


# Drawing Text
#### https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text

- `fillText` used to make solid text. Example from site.

    ```js
    //solid "Hello world".
    function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    ctx.font = '48px serif';
    ctx.fillText('Hello world', 10, 50);
    }
    ```

- `strokeText` to outline text

    ```js
    //outline "Hello world".
    function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    ctx.font = '48px serif';
    ctx.strokeText('Hello world', 10, 50);
    }
    ```

Can use this to play with font, textAlign, textBaseline, and direction. 