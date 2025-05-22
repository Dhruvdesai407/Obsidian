
# CSS 
## Tags:  #CSS #Webdev #revision #cheatsheet #Programming 
## Priority : #high

## Genre: [[Programming]]


> For it prerequisites check out: 

## Key Ideas & Details

* **Idea 1:** {{idea-1}}
    * *Supporting Detail/Example:* {{detail-1}}
    * **Related Notes:** 
* **Idea 2:** {{idea-2}}
    * *Supporting Detail/Example:* {{detail-2}}
    * **Related Tags:** 
* ... (Add more Key Ideas and Details as needed)








## Notes/Source:

`/* Comprehensive CSS Explanation */

# `/* ----------------------------------------------- */`
# `/* 1. Fonts and Typography */`
# `/* ----------------------------------------------- */`

# `/* Controls the appearance of text. */`

# `/* font-family: Specifies the font to use (with fallback options). */`
# `/* - Generic families: serif, sans-serif, monospace, cursive, fantasy, system-ui */`
# `/* - Web fonts can be imported using @font-face */`
# `/* Example: */`
# `body {`
  # `font-family: "Georgia", serif, sans-serif;`
# `}`

# /* font-size: Sets the size of the text. */
# `/* - Absolute units: px (pixels), pt (points), pc (picas) */`
# `/* - Relative units: em (relative to parent's font size), rem (relative to root element's font-size), vw/vh (viewport width/height), % */`
# `/* Example: */`
# `h1 {`
  # `font-size: 2.5em;`
# `}`

# /* font-weight: Controls the boldness of the text. */
# `/* - Keywords: normal (400), bold (700), bolder, lighter */`
# `/* - Numeric values: 100 to 900 (400 is normal, 700 is bold) */`
# `/* Example: */`
# `p {`
  # `font-weight: 500;`
# `}`

# `/* font-style: Sets the text style. */`
# `/* - Values: normal, italic, oblique */`
# `/* Example: */`
# `em {`
  # `font-style: italic;`
# `}`

# `/* line-height: Controls the spacing between lines of text. */`
# `/* - Unitless values are relative to the font size */`
# `/* Example: */`
# `body {`
  # `line-height: 1.6;`
# `}`

# `/* text-align: Aligns text within its container. */`
# `/* - Values: left, right, center, justify */`
# `/* Example: */`
# `.centered-text {`
  # `text-align: center;`
# `}`

# `/* text-decoration: Adds or removes text decorations. */`
# `/* - Values: none, underline, overline, line-through */`
# `/* Example: */`
# `a {`
  # `text-decoration: none;`
# `}`

# `/* letter-spacing: Adjusts the spacing between characters. */`
# `/* Example: */`
# `h2 {`
  # `letter-spacing: 2px;`
# `}`

# `/* word-spacing: Adjusts the spacing between words. */`
# `/* Example: */`
# `p {`
  # `word-spacing: 1px;`
# `}`

# `/* text-transform: Changes the capitalization of text. */`
# `/* - Values: none, uppercase, lowercase, capitalize */`
# `/* Example: */`
# `.uppercase {`
  # `text-transform: uppercase;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 2. Positioning */`
# `/* ----------------------------------------------- */`

# `/* Controls the placement of elements on the page. */`

# `/* static: Default positioning. Elements flow in their normal order. */`
# `/* top, right, bottom, left, and z-index have no effect. */`
# `/* Example: (This is the default, so you rarely write it explicitly) */`
# `div {`
  # `position: static;`
# `}`

# `/* relative: Positioned relative to its normal static position. */`
# `/* top, right, bottom, left shift the element without affecting the flow of other elements. */`
# `/* z-index can be used. */`
# `/* Example: */`
# `.relative {`
  # `position: relative;`
  # `top: 30px;`
  # `left: -10px;`
# `}`

# `/* absolute: Positioned relative to its closest positioned ancestor. */`
# `/* If no positioned ancestor, it's positioned relative to the <html> element. */`
# `/* Removed from the normal document flow, can overlap other elements. */`
# `/* top, right, bottom, left, and z-index are used. */`
# `/* Example: */`
# `.absolute-container {`
  # `position: relative; /* Needs a positioned ancestor! */`
  # `height: 200px;`
# `}`

# `.absolute {`
  # `position: absolute;`
  # `bottom: 0;`
  # `right: 0;`
# `}`

# `/* fixed: Positioned relative to the viewport (browser window). */`
# `/* Stays in the same place even when scrolling. */`
# `/* Removed from the normal document flow. */`
# `/* top, right, bottom, left, and z-index are used. */`
# `/* Example: */`
# `.fixed-nav {`
  # `position: fixed;`
  # `top: 0;`
  # `width: 100%;`
# `}`

# `/* sticky: A hybrid of relative and fixed. */`
# `/* Behaves like relative until it reaches a specified offset from the viewport edge, then becomes fixed. */`
# `/* Requires specifying top, right, bottom, or left. */`
# `/* Example: */`
# `.sticky {`
  # `position: sticky;`
  # `top: 10px;`
# `}`

# `/* z-index: Controls the stacking order of positioned elements. */`
# `/* Only works on elements with position: relative, absolute, fixed, or sticky. */`
# `/* Higher z-index values appear in front of lower values. */`
# `/* Example: */`
# `.overlay {`
  # `position: absolute;`
  # `z-index: 10;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 3. Colors */`
# `/* ----------------------------------------------- */`

# `/* Specifies the colors of elements. */`

# `/* color: Sets the foreground color of text. */`
# `/* - Named colors: red, blue, green, etc. (limited) */`
# `/* - Hex codes: #RRGGBB (e.g., #FF0000 for red) */`
# `/* - RGB: rgb(red, green, blue) (values from 0 to 255) */`
# `/* - RGBA: rgba(red, green, blue, alpha) (alpha for transparency, 0 to 1) */`
# `/* - HSL: hsl(hue, saturation, lightness) */`
# `/* - HSLA: hsla(hue, saturation, lightness, alpha) */`
# `/* Example: */`
# `body {`
  # `color: #333;`
# `}`

# `h1 {`
  # `color: rgb(255, 0, 0);`
# `}`

# `.transparent {`
  # `color: rgba(0, 0, 0, 0.5);`
# `}`

# `/* background-color: Sets the background color of an element. */`
# `/* Uses the same color values as the color property. */`
# `/* Example: */`
# `.highlight {`
  # `background-color: yellow;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 4. Shadows */`
# `/* ----------------------------------------------- */`

# `/* Adds shadow effects to elements. */`

# `/* box-shadow: Adds shadow to the box of an element. */`
# `/* - Syntax: h-offset v-offset blur spread color inset */`
# `/* - h-offset: Horizontal offset of the shadow (positive = right, negative = left) */`
# `/* - v-offset: Vertical offset of the shadow (positive = down, negative = up) */`
# `/* - blur: Blur radius (higher values = more blur) */`
# `/* - spread: Spread radius (positive values increase the shadow size) */`
# `/* - color: Shadow color */`
# `/* - inset: (Optional) Makes the shadow an inner shadow */`
# `/* Example: */`
# `.shadow {`
  # `box-shadow: 5px 5px 10px 0px rgba(0, 0, 0, 0.5);`
# `}`

# `.inner-shadow {`
  # `box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.7);`
# `}`

# `/* text-shadow: Adds shadow to text. */`
# `/* - Syntax: h-offset v-offset blur color */`
# `/* Example: */`
# `h1 {`
  # `text-shadow: 2px 2px 4px #000000;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 5. Flexbox (One-Dimensional Layout) */`
# `/* ----------------------------------------------- */`

# `/* Arranges items in one dimension (row or column). */`

# `/* display: flex | inline-flex;: Defines the container as a flex container. */`
# `.container {`
  # `display: flex;`
# `}`

# `/* flex-direction: row | row-reverse | column | column-reverse;: Sets the direction of the main axis. */`
# `.container {`
  # `flex-direction: column;`
# `}`

# `/* flex-wrap: nowrap | wrap | wrap-reverse;: Controls whether items wrap to multiple lines. */`
# `.container {`
  # `flex-wrap: wrap;`
# `}`

# `/* flex-flow: <flex-direction> || <flex-wrap> Shorthand. */`
# `.container {`
  # `flex-flow: row wrap;`
# `}`

# `/* justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;: Aligns items along the main axis. */`
# `.container {`
  # `justify-content: center;`
# `}`

# `/* align-items: stretch | flex-start | flex-end | center | baseline;: Aligns items along the cross axis. */`
# `.container {`
  # `align-items: center;`
# `}`

# `/* align-content: stretch | flex-start | flex-end | center | space-between | space-around | space-evenly;: Aligns flex lines when there are multiple lines. */`
# `.container {`
  # `align-content: space-between;`
# `}`

# `/* order: <number>;: Controls the order in which items appear. */`
# `.item {`
  # `order: 2;`
# `}`

# `/* flex-grow: <number>;: How much an item should grow relative to others. */`
# `.item {`
  # `flex-grow: 1;`
# `}`

# `/* flex-shrink: <number>;: How much an item should shrink relative to others. */`
# `.item {`
  # `flex-shrink: 0;`
# `}`

# `/* flex-basis: <length> | auto;: Initial size of an item. */`
# `.item {`
  # `flex-basis: 200px;`
# `}`

# `/* flex: <flex-grow> <flex-shrink> <flex-basis> | auto | none;: Shorthand. */`
# `.item {`
  # `flex: 1 1 auto;`
# `}`

# `/* align-self: auto | flex-start | flex-end | center | baseline | stretch;: Overrides align-items for a single item. */`
# `.item {`
  # `align-self: center;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 6. Grid (Two-Dimensional Layout) */`
# `/* ----------------------------------------------- */`

# `/* Creates two-dimensional layouts (rows and columns). */`

# `/* display: grid | inline-grid;: Defines the container as a grid. */`
# `.container {`
  # `display: grid;`
# `}`

# `/* grid-template-rows: <track-size> ...;: Defines row heights. */`
# `.container {`
  # `grid-template-rows: 100px auto 1fr;`
# `}`

# `/* grid-template-columns: <track-size> ...;: Defines column widths. */`
# `.container {`
  # `grid-template-columns: 200px 1fr 2fr;`
# `}`

# `/* grid-template-areas: "<row1-names>" "<row2-names>" ...;: Defines grid areas by name. */`
# `.container {`
  # `grid-template-areas:`
    # `"header header header"`
    # `"sidebar main main"`
    # `"footer footer footer";`
# `}`

# `/* grid-template: <grid-template-rows> / <grid-template-columns>;: Shorthand. */`
# `.container {`
  # `grid-template: 100px auto / 200px 1fr;`
# `}`

# `/* grid-gap: <grid-row-gap> <grid-column-gap>;: Shorthand for row and column gaps. */`
# `.container {`
  # `grid-gap: 10px 20px;`
# `}`

# `/* grid-row-gap: <length>;: Gap between rows. */`
# `.container {`
  # `grid-row-gap: 15px;`
# `}`

# `/* grid-column-gap: <length>;: Gap between columns. */`
# `.container {`
  # `grid-column-gap: 25px;`
# `}`

# `/* justify-items: stretch | start | end | center;: Aligns items horizontally within their cells. */`
# `.container {`
  # `justify-items: center;`
# `}`

# `/* align-items: stretch | start | end | center;: Aligns items vertically within their cells. */`
# `.container {`
  # `align-items: end;`
# `}`

# `/* justify-content: start | end | center | stretch | space-around | space-between | space-evenly;: Aligns the grid horizontally within the container. */`
# `.container {`
  # `justify-content: space-around;`
# `}`

# `/* align-content: start | end | center | stretch | space-around | space-between | space-evenly;: Aligns the grid vertically within the container. */`
# `.container {`
  # `align-content: space-between;`
# `}`

# `/* grid-auto-rows: <track-size> ...;: Size of implicitly created rows. */`
# `/* grid-auto-columns: <track-size> ...;: Size of implicitly created columns. */`
# `/* grid-auto-flow: row | column | row dense | column dense;: How auto-placed items are inserted. */`

# `/* grid-column-start: <number> | <name> | span <number> | span <name> | auto;: Starting column line. */`
# `/* grid-column-end: <number> | <name> | span <number> | span <name> | auto;: Ending column line. */`
# `/* grid-row-start: <number> | <name> | span <number> | span <name> | auto;: Starting row line. */`
# `/* grid-row-end: <number> | <name> | span <number> | span <name> | auto;: Ending row line. */`
# `.item {`
  # `grid-column-start: 1;`
  # `grid-column-end: 3;`
  # `grid-row-start: 2;`
  # `grid-row-end: 3;`
# `}`

# `/* grid-column: <grid-column-start> / <grid-column-end>;: Shorthand. */`
# `/* grid-row: <grid-row-start> / <grid-row-end>;: Shorthand. */`
# `.item {`
  # `grid-column: 1 / 3;`
  # `grid-row: 2 / 3;`
# `}`

# `/* grid-area: <row-start> / <column-start> / <row-end> / <column-end> | <name>;: Shorthand or named area. */`
# `.item {`
  # `grid-area: header;`
# `}`

# `/* justify-self: start | end | center | stretch;: Horizontal alignment within a cell (overrides justify-items). */`
# `/* align-self: start | end | center | stretch;: Vertical alignment within a cell (overrides align-items). */`

# `/* ----------------------------------------------- */`
# `/* 7. Transitions */`
# `/* ----------------------------------------------- */`

# `/* Smooth animations between CSS property values. */`

# `/* transition-property: none | all | <property>[, <property>, ...];: Properties to transition. */`
# `.element {`
  # `transition-property: background-color, color;`
# `}`

# `/* transition-duration: <time>[, <time>, ...];: Duration of the transition(s). */`
# `.element {`
  # `transition-duration: 0.3s, 0.5s;`
# `}`

# `/* transition-timing-function: ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>);: Speed curve. */`
# `.element {`
  # `transition-timing-function: ease-in-out;`
# `}`

# `/* transition-delay: <time>[, <time>, ...];: Delay before transition(s) start. */`
# `.element {`
  # `transition-delay: 0.1s;`
# `}`

# `/* transition: <transition-property> <transition-duration> <transition-timing-function> <transition-delay>;: Shorthand. */`
# `.element {`
  # `transition: all 0.3s ease-in-out;`
# `}`

# `/* ----------------------------------------------- */`
# `/* 8. Animations */`
# `/* ----------------------------------------------- */`

# `/* More complex, multi-step animations. */`

# `/* @keyframes <animation-name> { ... }: Defines the animation sequence. */`
# `@keyframes fadeIn {`
  # `0% {`
    # `opacity: 0;`
  # `}`
  # `100% {`
    # `opacity: 1;`
  # `}`
# `}`

# `/* animation-name: <animation-name> | none;: Name of the @keyframes animation. */`
# `.element {`
  # `animation-name: fadeIn;`
# `}`

# `/* animation-duration: <time>;: Duration of one animation cycle. */`
# `.element {`
  # `animation-duration: 1s;`
# `}`

# `/* animation-timing-function: ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>);: Speed curve. */`
# `.element {`
  # `animation-timing-function: linear;`
# `}`

# `/* animation-delay: <time>;: Delay before animation starts. */`
# `.element {`
  # `animation-delay: 0.5s;`
# `}`

# `/* animation-iteration-count: <number> | infinite;: How many times to play. */`
# `.element {`
  # `animation-iteration-count: infinite;`
# `}`

# `/* animation-direction: normal | reverse | alternate | alternate-reverse;: Direction of the animation. */`
# `.element {`
  # `animation-direction: alternate;`
# `}`

# `/* animation-fill-mode: none | forwards | backwards | both;: Styles before/after animation. */`
# `.element {`
  # `animation-fill-mode: forwards;`
# `}`

# `/* animation-play-state: running | paused;: Running or paused. */`
# `.element:hover {`
  # `animation-play-state: paused;`
# `}`

# `/* animation: <animation>`



## Questions for Active Recall

* What is the main principle behind this concept?
* How does this relate to?
* Can I explain this in my own words?
* What are some real-world examples of this?
## Potential Connections & Further Exploration


## My Understanding (Self-Assessment)

*(Briefly reflect on your current understanding of this topic)*

