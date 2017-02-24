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
