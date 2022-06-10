# CLASS-12

## HTML & JAVASCRIPT CANVAS

The html `<canvas>` element allows us to draw 2D graphics using JavaScript. It requires at least two attributes, `width` and `height`. We can use DOM to access its properties and can change the attributes using the DOM methods (e.g.)

```html
<canvas width="500" height="300" id="canvas"></canvas>
```

```javascript
canvas.width = 600;
canvas.height = 400;
```

**Fallback Content:** The `<canvas>` element requires a closing tag `</canvas>`. The content between the tags is fallback content that will display only if the browser doesn’t support the element. Most modern browser support it nowadays.

**The Rendering Context:** To draw something we need to access the rendering context.

* `getContext()` Method featured in the `<canvas>` element that returns a render context object. Takes one argument which is the type of context. For example `"2d"` to get a 2D rendering context object. The 2D rendering context allows us to draw shapes, text, images, and other objects. It is important to check if the browser supports the `getContext()` method. (e.g.)

```JavaScript
if(canvas.getContext) {
  let ctx = main.getContext('2d');
}
```

**The 2D Context:** We can draw simple 2D shapes, rectangles, and arcs. The coordinates begin at the upper-left of the element, which is point `(0,0)` with `x` increasing to the right and `y` increasing to the bottom.

**Fills and Stokes:** Fill and Stroke are two basic drawing operations on 2D drawing context:

* The `fillStyle` property shapes fills with a specific style.
* The `strokeStyle` property adds colors to the edges of the shape.

***

## CHART.js

Chart.js is a JavaScript plugin that uses the html `<canvas>` element to draw graphs onto a page. It makes it easier to use all kinds of bar charts, line charts, pie charts and more.

In order to use Chart.js in a project we need to download it first, copy the `Chart.min.js.` file into the directory we will be working on, create a new html page and import the script. (e.g.)

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

**Chart Types:**
  
  1. Line Chart
  2. Pie Chart
  3. Bar Chart

> Advantages of Charts over Tables

* Can create animated Charts.
* Better for displaying data visually.
* No need for layout tools.
* Easier to look at and convey data quickly.
* Simple to use and more flexible.

*All those advantages over tables can definitely improve my previously created applications visually.*

***

### Things I want to know more about

* How to use Chart.js properly and efficiently. 

***

[-back](https://alexriverau.github.io/reading-notes/)
