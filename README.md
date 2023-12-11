# Shivam-Raj_CPT
Document Type Declaration (DOCTYPE):

html

<!DOCTYPE html>
This declaration defines the document type and version of HTML being used. In this case, it's HTML5.

HTML Document Structure:

html

<html lang="en">
This tag defines the beginning of the HTML document. The lang attribute specifies the language of the document as English.

Head Section:

html

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Video Conferencing Platform</title>
</head>
Charset Meta Tag: Specifies the character set of the HTML document as UTF-8.
Viewport Meta Tag: Configures the viewport settings for better responsiveness on various devices.
Title Tag: Sets the title of the web page, which appears in the browser tab.
Styles:

html

<style>
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
    }

    #localVideo, #remoteVideo {
        max-width: 100%;
        margin-right: 20px;
    }

    #video-container {
        display: flex;
    }
</style>
Body Styles: The body styles use Flexbox to center its content both horizontally and vertically. The height: 100vh ensures that the body takes up the full height of the viewport, and margin: 0 removes any default margin.
Video Styles: The max-width: 100% ensures that the videos don't exceed the width of their container, and margin-right: 20px adds a margin to the right side of the videos.
Video Container Styles: The display: flex property is applied to the video container to arrange its children (videos) in a row.
Body Section:

html

<body>
    <div id="video-container">
        <video id="localVideo" autoplay muted playsinline></video>
        <video id="remoteVideo" autoplay playsinline></video>
    </div>

    <script>
        // JavaScript code
    </script>
</body>
Video Container: Contains two video elements with the IDs localVideo and remoteVideo.
Video Elements: The videos have attributes like autoplay (automatically start playing), muted (for the local video to mute its audio), and playsinline (enables inline playback on iOS).
JavaScript Section:

javascript

<script>
    document.addEventListener('DOMContentLoaded', () => {
        const localVideo = document.getElementById('localVideo');
        const remoteVideo = document.getElementById('remoteVideo');

        navigator.mediaDevices.getUserMedia({ video: true, audio: true })
            .then((stream) => {
                localVideo.srcObject = stream;
            })
            .catch((error) => {
                console.error('Error accessing media devices:', error);
            });
    });
</script>
Event Listener: Listens for the DOMContentLoaded event, indicating that the HTML document has been fully loaded.
Getting Media Devices: Uses the navigator.mediaDevices.getUserMedia API to access the user's camera and microphone.
Assigning Stream: If successful, the obtained media stream is assigned to the srcObject property of the localVideo element.
Error Handling: If there's an error, it is logged to the console.
In summary, this code creates a simple video conferencing interface with two video elements, where the local video stream (user's camera and microphone) is displayed in one video element, and the remote video stream (potentially from another participant) is displayed in another. The layout is styled using CSS, and basic media capture and display functionality is implemented using JavaScript.
