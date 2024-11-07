---
layout: null
title: Game Leaks
permalink: /leaks
weight: 4
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >

<style>
body, html {
  margin: 0;
  padding: 0;
  overflow: hidden; /* Hide scrollbars to ensure fullscreen video */
  height: 100%;
  width: 100%;
  background: black;
}

#videoContainer {
  display: none;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  z-index: 10; /* Ensure the video is on top */
}

#videoContainer video {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensure the video covers the entire container */
}

#playButton {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 20px;
  font-size: 20px;
  cursor: pointer;
  background-color: #FF4500;
  color: white;
  border: none;
  z-index: 20; /* Ensure the button is above other elements */
}
</style>

<div id="videoContainer">
  <video id="surpriseVideo" src="/sounds/Never.mp4"></video>
</div>

<button id="playButton" onclick="playVideo()">Click to get the leaks!</button>

<script>
  function playVideo() {
    var videoContainer = document.getElementById("videoContainer");
    var video = document.getElementById("surpriseVideo");
    var playButton = document.getElementById("playButton");

    // Hide the button and show the video container
    playButton.style.display = "none";
    videoContainer.style.display = "block";

    // Request full screen
    if (videoContainer.requestFullscreen) {
      videoContainer.requestFullscreen();
    } else if (videoContainer.mozRequestFullScreen) { /* Firefox */
      videoContainer.mozRequestFullScreen();
    } else if (videoContainer.webkitRequestFullscreen) { /* Chrome, Safari & Opera */
      videoContainer.webkitRequestFullscreen();
    } else if (videoContainer.msRequestFullscreen) { /* IE/Edge */
      videoContainer.msRequestFullscreen();
    }

    // Play the video
    video.play();

    // Refresh the page when the video ends
    video.addEventListener('ended', function() {
      location.reload();
    });
  }

  // Disable right-click context menu
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>
