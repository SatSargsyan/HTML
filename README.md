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
