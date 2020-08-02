# CSS Transforms, Transitions, and Animations

# What Google Learned From Its Quest to Build the Perfect Team (https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)
Employee performance optimization: analyzing and improving individual workers.
Managers and employee collaboration has increased 50 percent in the past two decades. 3/4+ of the day is communicating with colleagues.

Working in teams is encouraged in places. Studies show it produces better results, problem solving and increases job satisfaction. Some cases, collaboration positively impacts profits. 

Research study showed, that result were all or nothing. If a team did well on one assignment, they tended to succeed on all the assignments given to them. 
    - "Good team" traits: overall, everyone speaks about the same amount. Sometimes this means rotating leadership for tasks.
    - collective intelligence declined when only one person talked.
    - Psychological safety: members feeling safe to share and not worried about needing to be embarrassed. Mutual respect and trust.
    - Clear goal, but psychological safety was more important.

# CSS Transforms (https://learn.shayhowe.com/advanced-html-css/css-transforms/)
Rotate: `transform: rotate(20deg);`
Scale: `transform: scale(.75);`
Height/Width: `transform: scaleY(1.15);` scaleX or scaleY
Skew: Example using 3 boxes.

  ```css
  .box-1 {
  transform: skewX(5deg);
  }
  .box-2 {
  transform: skewY(-20deg);
  }
  .box-3 {
  transform: skew(5deg, -20deg);
  }
  ```

Can combine: `transform: skew(10deg, 20deg) translateX(20px);`
Cube using CSS: From site

```css
.cube {
position: relative;
}
.side {
height: 95px;
position: absolute;
width: 95px;
}
.top {
background: #9acc53;
transform: rotate(-45deg) skew(15deg, 15deg);
}
.left {
background: #8ec63f;
transform: rotate(15deg) skew(15deg, 15deg) translate(-50%, 100%);
}
.right {
background: #80b239;
transform: rotate(-15deg) skew(-15deg, -15deg) translate(50%, 100%);
}
```

Can transform origin: Combined with other transform.

```css
.box-4 {
transform: scale(.75) translate(-10px, -10px);
transform-origin: 20px 50px;
}
```

Change perspective: `transform: perspective(200px) rotateX(45deg);`
3D Rotate: `transform: perspective(200px) rotateZ(45deg);`
3D Scale: `transform: perspective(200px) scaleZ(.25) rotateX(45deg);`
3D Translate
3D Skew
Backface Visibility#backface-visibility - flip it around 180

# CSS Transitions and Animations (https://learn.shayhowe.com/advanced-html-css/transitions-animations/)
Transitions: fade to another color on hover. From site

```css
.box {
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
```

Note: Not all properties can be transitioned. 

Can have a transition-delay before transition occurs. 

Shorthand for delayed transition transition from site. Curves corners of box to become a circle. 

```css
.box {
  background: #2db34a;
  border-radius: 6px;
  transition: background .2s linear, border-radius 1s ease-in 1s;
}
.box:hover {
  color: #ff7b29;
  border-radius: 50%;
}
```

Can rotate a card on hover. Example code from site. 

```html
<div class="card-container">
  <div class="card">
    <div class="side">...</div>
    <div class="side back">...</div>
  </div>
</div>

```

```css
.card-container {
  height: 150px;
  perspective: 600;
  position: relative;
  width: 150px;
}
.card {
  height: 100%;
  position: absolute;
  transform-style: preserve-3d;
  transition: all 1s ease-in-out;
  width: 100%;
}
.card:hover {
  transform: rotateY(180deg);
}
.card .side {
  backface-visibility: hidden;
  height: 100%;
  position: absolute;
  width: 100%;
}
.card .back {
  transform: rotateY(180deg);
}
```

Animation Keyframes (`@keyframes`)
Set multiple points an element should go through a transition. 
Example code for making a ball bounce from the top left, center, and to top right.

```css
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```

Shorthand for animation. Starting at paused. 

```css
.stage:hover .ball {
  animation: slide 2s ease-in-out .5s infinite alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```

# Buttons (https://codepen.io/retyui/pen/ByoaXV)
Example code for 3 floating bottoms that move when not hovered over. When hovered over, the buttons pause animation and change color. 

# CSS3 Keyframes Animation (https://codepen.io/akshaychauhan/pen/oAfae)
Example code for a red bouncing ball, getting closer to ground with each bounce. Uses keyframes.


# 404 (https://codepen.io/kieranfivestars/pen/MYdQxX)
Example code for an animated 404 message where the numbers scale in and out and switch pages. 

# Pure CSS Bounce Animation (https://codepen.io/dp_lewis/pen/gCfBv)
Example of a ball bouncing and changing shape. Turns into a square with a giant purple circle around it. Then it falls off the bottom off the bottom of the screen. Continues to repeat. 
