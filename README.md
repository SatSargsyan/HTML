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
Try It Yourself

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
