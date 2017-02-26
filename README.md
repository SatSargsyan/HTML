# HTML

Audio on the Web

The <audio> element creates an audio player inside the browser.
<audio controls>
   <source src="audio.mp3" type="audio/mpeg">
   <source src="audio.ogg" type="audio/ogg">
   Audio element not supported by your browser. 
</audio>

The text in beetween the audio tags is for not supported browsers

###Attributes of <audio>

controls
Specifies that audio controls should be displayed (such as a play/pause button, etc.)

autoplay
When this attribute is defined, audio starts playing as soon as it is ready, without asking for the visitor's permission.
<audio controls autoplay>
Try It Yourself

loop
This attribute is used to have the audio replay every time it is finished.
<audio controls autoplay loop>


Currently, there are three supported file formats for the <audio> element: MP3, WAV, and OGG.
Videos in HTML

The video element is similar to the audio element. 
You can specify the video source URL using an attribute in a video element, or using source elements inside the video element:
<video controls>
   <source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   Video is not supported by your browser
</video>



Another aspect that the audio and video elements have in common is that the major browsers do not all support the same file types. If the browser does not support the first video type, it will try the next one.

Attributes of <video>

Another aspect shared by both the audio and the video elements is that each has controls, autoplay and loop attributes. 

In this example, the video will replay after it finishes playing:
<video controls autoplay loop>
   <source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   Video is not supported by your browser
</video>
Try It Yourself

Currently, there are three supported video formats for the <video> element: MP4, WebM, and OGG.

Progress Bar

The <progress> element provides the ability to create progress bars on the web.
The progress element can be used within headings, paragraphs, or anywhere else in the body.

Progress Element Attributes
Value: Specifies how much of the task has been completed. 
Max: Specifies how much work the task requires in total.

Example:
Status: <progress min="0" max="100" value="35">
</progress>

Use the <progress> tag in conjunction with JavaScript to dynamically display a task's progress.

HTML5 Web Storage

With HTML5 web storage, websites can store data on a user's local computer. 
Before HTML5, we had to use JavaScript cookies to achieve this functionality. 

The Advantages of Web Storage
- More secure
- Faster
- Stores a larger amount of data
- Stored data is not sent with every server request
Local storage is per domain. All pages from one domain can store and access the same data.

Types of Web Storage Objects

There are two types of web storage objects:
- sessionStorage()
- localStorage()

Local vs. Session
- Session Storage is destroyed once the user closes the browser
- Local Storage stores data with no expiration date
You need to be familiar with basic JavaScript in order to understand and use the API.

Working with Values

The syntax for web storage for both local and session storage is very simple and similar.
The data is stored as key/value pairs.

Storing a Value:
localStorage.setItem("key1", "value1");

Getting a Value:
//this will print the value
alert(localStorage.getItem("key1")); 

Removing a Value:
localStorage.removeItem("key1");

Removing All Values:
localStorage.clear();

The same syntax applies to the session storage, with one difference: Instead of localStorage, sessionStorage is used.

What is the Geolocation API?

In HTML5, the Geolocation API is used to obtain the user's geographical location.

Since this can compromise user privacy, the option is not available unless the user approves it.

Geolocation is much more accurate for devices with GPS, like smartphones and the like.

Using HTML Geolocation

The Geolocation API’s main method is getCurrentPosition, which retrieves the current geographic location of the user's device.
navigator.geolocation.getCurrentPosition();

Parameters:
showLocation (mandatory): Defines the callback method that retrieves location information.
ErrorHandler(optional): Defines the callback method that is invoked when an error occurs in processing the asynchronous call.
Options (optional): Defines a set of options for retrieving the location information.
You need to be familiar with basic JavaScript in order to understand and use the API.

Presenting Data

User location can be presented in two ways: Geodetic and Civic.

1. The geodetic way to describe position refers directly to latitude and longitude.
2. The civic representation of location data is presented in a format that is more easily read and understood by the average person.

Each parameter has both a geodetic and a civic representation:
nkar html1 anunov

The getCurrentPosition() method returns an object if it is successful. The latitude, longitude, and accuracy properties are always returned.

Making Elements Draggable

The drag and drop feature lets you "grab" an object and drag it to a different location.
To make an element draggable, just set the draggable attribute to true:
<img draggable="true" />

Any HTML element can be draggable.

The API for HTML5 drag and drop is event-based.

Example:
<!DOCTYPE HTML>
<html>
   <head>
   <script>
function allowDrop(ev) {
    ev.preventDefault();
}

function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}
   </script>
   </head>
<body>

   <div id="box" ondrop="drop(event)"
   ondragover="allowDrop(event)"
   style="border:1px solid black; 
   width:200px; height:200px"></div>

   <img id="image" src="sample.jpg" draggable="true"
   ondragstart="drag(event)" width="150" height="50" alt="" />

</body>
</html>

What to Drag
When the element is dragged, the ondragstart attribute calls a function, drag(event), which specifies what data is to be dragged.
The dataTransfer.setData() method sets the data type and the value of the dragged data:
function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}

In our example, the data type is "text" and the value is the ID of the draggable element ("image").

Where to Drop
The ondragover event specifies where the dragged data can be dropped. By default, data and elements cannot be dropped in other elements. To allow a drop, we must prevent the default handling of the element.
This is done by calling the event.preventDefault() method for the ondragover event.

Do the Drop
When the dragged data is dropped, a drop event occurs.
In the example above, the ondrop attribute calls a function, drop(event):
function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}

The preventDefault() method prevents the browser's default handling of the data (default is open as link on drop).
The dragged data can be accessed with the dataTransfer.getData() method. This method will return any data that was set to the same type in the setData() method.
The dragged data is the ID of the dragged element ("image").

At the end, the dragged element is appended into the drop element, using the appendChild() function.
Basic knowledge of JavaScript is required to understand and use the API.


Drawing Shapes

SVG stands for Scalable Vector Graphics, and is used to draw shapes with HTML-style markup.

It offers several methods for drawing paths, boxes, circles, text, and graphic images. 

SVG is not pixel-based, so it can be magnified infinitely with no loss of quality.

Inserting SVG Images

An SVG image can be added to HTML code with just a basic image tag that includes a source attribute pointing to the image:
<img src="image.svg" alt="" height="300" />

Drawing a Circle

To draw shapes with SVG, you first need to create an SVG element tag with two attributes: width and height.
<svg width="1000" height="1000"></svg>

To create a circle, add a <circle> tag:
<svg width="2000" height="2000">
   <circle cx="80" cy="80" r="50" fill="green" />
</svg>


- cx pushes the center of the circle further to the right of the screen
- cy pushes the center of the circle further down from the top of the screen
- r defines the radius
- fill determines the color of our circle
- stroke adds an outline to the circle

Other Shape Elements

<rect> defines a rectangle:
<svg width="2000" height="2000">
   <rect width="300" height="100" 
     x="20" y="20" fill="green" />
</svg>

<line> defines a line segment:
<svg width="400" height="410">
    <line x1="10" y1="10" x2="200" y2="100" 
        style="stroke:#000000; stroke-linecap:round; 
        stroke-width:20"  />
</svg>

(x1, y1) define the start coordinates(x2, y2) define the end coordinates.

<polyline> defines shapes built from multiple line definitions:
<svg width="2000" height="500">
    <polyline style="stroke-linejoin:miter; stroke:black; 
        stroke-width:12; fill: none;"
        points="100 100, 150 150, 200 100" />
</svg>

Points are the polyline's coordinates.
The code below will draw a black check sign:


<ellipse> and <polygon>

Ellipse
The <ellipse> is similar to the <circle>, with one exception: 
You can independently change the horizontal and vertical axes of its radius, using the rx and ry attributes.
<svg height="500" width="1000">
   <ellipse cx="200" cy="100" rx="150" ry="70" style="fill:green" />
</svg>

Polygon 
The <polygon> element is used to create a graphic with at least three sides. The polygon element is unique because it automatically closes off the shape for you.
<svg width="2000" height="2000">
<polygon points="100 100, 200 200, 300 0" 
      style="fill: green; stroke:black;" />
</svg>



26.05.2017
Shape Animations

SVG animations can be created using the <animate> element. 

The example below creates a rectangle that will change its position in 3 seconds and will then repeat the animation twice:
<svg width="1000" height="250">
<rect width="150" height="150" fill="orange">
  <animate attributeName="x" from="0" to="300"
    dur="3s" fill="freeze" repeatCount="2"/> 
</rect>
</svg>
Try It Yourself

attributeName: Specifies which attribute will be affected by the animation
from: Specifies the starting value of the attribute
to: Specifies the ending value of the attribute
dur: Specifies how long the animation runs (duration)
fill: Specifies whether or not the attribute's value should return to its initial value when the animation is finished (Values: "remove" resets the value; "freeze" keeps the “to value”)
repeatCount: Specifies the repeat count of the animation

In the example above, the rectangle changes its x attribute from 0 to 300 in 3 seconds.
To repeat the animation indefinitely, use the value "indefinite" for the repeatCount attribute.

Paths

The <path> element is used to define a path.

The following commands are available for path data:
M: moveto
L: lineto
H: horizontal lineto
V: vertical lineto
C: curveto
S: smooth curveto
Q: quadratic Bézier curve
T: smooth quadratic Bézier curveto
A: elliptical Arc
Z: closepath

Define a path using the d attribute:
<svg width="500" height="500">
<path d="M 0 0 L200 200 L200 0 Z" style="stroke:#000;  fill:none;" />
</svg>

M places our "virtual pen" down at the position 0, 0. It then moves 200px down and to the right, then moves up to the position 200, 0. The Z command closes the shape, which results in a hypotenuse:

All of the above commands can also be expressed with lower case letters. When capital letters are used, it indicates absolute position; lower case indicates relative position.

The <canvas> Element

The HTML canvas is used to draw graphics that include everything from simple lines to complex graphic objects.

The <canvas> element is defined by:
<canvas id="canvas1" width="200" height="100">
</canvas>

The <canvas> element is only a container for graphics. You must use a script to actually draw the graphics (usually JavaScript).

The <canvas> element must have an id attribute so it can be referred to by JavaScript:
<html>
   <head></head>
   <body>
     <canvas id="canvas1" 
   width="400" height="300"></canvas> 

   <script>
      var can = document.getElementById("canvas1"); 
      var ctx = can.getContext("2d");
   </script>

   </body>
</html>

getContext() returns a drawing context on the canvas.
Basic knowledge of JavaScript is required to understand and use the Canvas.


Canvas Coordinates

The HTML canvas is a two-dimensional grid.
The upper-left corner of the canvas has the coordinates (0,0).

X coordinate increases to the right.
Y coordinate increases toward the bottom of the canvas.


Drawing Shapes

The fillRect(x, y, w, h) method draws a "filled" rectangle, in which w indicates width and h indicates height. The default fill color is black. 

A black 100*100 pixel rectangle is drawn on the canvas at the position (20, 20):
var c=document.getElementById("canvas1");
var ctx=c.getContext("2d");
ctx.fillRect(20,20,100,100);

The fillStyle property is used to set a color, gradient, or pattern to fill the drawing.
Using this property allows you to draw a green-filled rectangle.
var canvas=document.getElementById("canvas1");
var ctx=canvas.getContext("2d");
ctx.fillStyle ="rgba(0, 200, 0, 1)";
ctx.fillRect (36, 10, 22, 22);

The canvas supports various other methods for drawing:

Draw a Line
moveTo(x,y): Defines the starting point of the line.
lineTo(x,y): Defines the ending point of the line.

Draw a Circle
beginPath(): Starts the drawing.
arc(x,y,r,start,stop): Sets the parameters of the circle.
stroke(): Ends the drawing.

Gradients
createLinearGradient(x,y,x1,y1): Creates a linear gradient.
createRadialGradient(x,y,r,x1,y1,r1): Creates a radial/circular gradient.

Drawing Text on the Canvas
Font: Defines the font properties for the text.
fillText(text,x,y): Draws "filled" text on the canvas.
strokeText(text,x,y): Draws text on the canvas (no fill).
There are many other methods aimed at helping to draw shapes and images on the canvas.


Canvas vs. SVG

Canvas
- Elements are drawn programmatically
- Drawing is done with pixels
- Animations are not built in
- High performance for pixels-based drawing operations
- Resolution dependent
- No support for event handlers
- You can save the resulting image as .png or .jpg
- Well suited for graphic-intensive games

SVG
- Elements are part of the page's DOM (Document object model)
- Drawing is done with vectors
- Effects, such as animations are built in
- Based on standard XML syntax, which provides better accessibility
- Resolution independent
- Support for event handlers
- Not suited for game applications
- Best suited for applications with large rendering areas (for example, Google Maps)

You can actually use both SVG and canvas on the same page, if needed.
However, you cannot just draw SVG onto a canvas, or vice-versa.

Working with Canvas

The Canvas element can be transformed. As an example, a text is written on the canvas at the coordinates (20, 10).
ctx.font="bold 22px Tahoma";
ctx.textAlign="start";
ctx.fillText("start", 10, 30);

The translate(x,y) method is used to move the Canvas.
x indicates how far to move the grid horizontally, and y indicates how far to move the grid vertically.
ctx.translate(100, 150);
ctx.fillText("after translate", 10, 30);
Try It Yourself

In this example, the canvas is moved 100px to the right, and 150px down.
Result:

The rotate() Method

The rotate() method is used to rotate the HTML5 Canvas. The value must be in radians, not degrees.

Here is an example that draws the same rectangle before and after rotation is set:
ctx.fillStyle = "#FF0000";
ctx.fillRect(10,10, 100, 100);

ctx.rotate( (Math.PI / 180) * 25);  //rotate 25 degrees.

ctx.fillStyle = "#0000FF";
ctx.fillRect(10,10, 100, 100);

HTML5 Forms

HTML5 brings many features and improvements to web form creation. There are new attributes and input types that were introduced to help create better experiences for web users.

Form creation is done in HTML5 the same way as it was in HTML4:
<form>
   <label>Your name:</label>
   <input id="user" name="username" type="text" />
</form>


New Attributes

HTML5 has introduced a new attribute called placeholder. On <input> and <textarea> elements, this attribute provides a hint to the user of what information can be entered into the field.
<form>
   <label for="email">Your e-mail address: </label> 
   <input type="text" name="email" placeholder="email@example.com" /> 
</form>


The autofocus attribute makes the desired input focus when the form loads:
<form>
   <label for="e-mail">Your e-mail address: </label> 
   <input type="text" name="email" autofocus/>
</form>



Forms with Required Fields

The "required" attribute is used to make the input elements required.
<form autocomplete="off">
   <label for="e-mail">Your e-mail address: </label>
   <input name="Email" type="text" required />
   <input type="submit" value="Submit"/>
</form>

The form will not be submitted without filling in the required fields.

The autocomplete attribute specifies whether a form or input field should have autocomplete turned on or off.
When autocomplete is on, the browser automatically complete values based on values that the user has entered before.


HTML5 added several new input types:
- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

New input attributes in HTML5:
- autofocus
- form
- formaction
- formenctype
- formmethod
- formnovalidate
- formtarget
- height and width
- list
- min and max
- multiple
- pattern (regexp)
- placeholder
- required
- step
Input types that are not supported by old web browsers, will behave as input type text.

Creating a Search Box

The new search input type can be used to create a search box:
<input id="mysearch" name="searchitem" type="search" />


Search Options

The <datalist> tag can be used to define a list of pre-defined options for the search field:
<input id="car" type="text" list="colors" />
<datalist id="colors">
   <option value="Red">
   <option value="Green">
   <option value="Yellow">
</datalist>


<option> defines the options in a drop-down list for the user to select. 
The ID of the datalist element must match with the list attribute of the input box.



Creating More Fields

Some other new input types include email, url, and tel:
<input id="email" name="email" type="email" placeholder="example@example.com" />
<br />
<input id="url" name="url" type="url" placeholder="example.com" />
<br />
<input id="tel" name="tel" type="tel" placeholder="555.555.1211" />

These are especially useful when opening a page on a modern mobile device, which recognizes the input types and opens a corresponding keyboard matching the field's type:

nkar html2
These new types make it easier to structure and validate HTML forms.




