---
layout: default
title: Game Leaks
permalink: /leaks
weight: 4
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
{% include landing.html %}

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
</style>

<div id="videoContainer">
  <video id="surpriseVideo" src="/sounds/Never.mp4"></video>
</div>

<script>
  function playVideo() {
    var videoContainer = document.getElementById("videoContainer");
    var video = document.getElementById("surpriseVideo");

    // Display the video container
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

  document.addEventListener("DOMContentLoaded", function() {
    // Create a button to trigger video playback
    var playButton = document.createElement("button");
    playButton.style.position = "fixed";
    playButton.style.top = "50%";
    playButton.style.left = "50%";
    playButton.style.transform = "translate(-50%, -50%)";
    playButton.style.padding = "20px";
    playButton.style.fontSize = "20px";
    playButton.style.cursor = "pointer";
    playButton.textContent = "Click to play video";
    playButton.onclick = function() {
      playVideo();
      playButton.style.display = "none"; // Hide the button after clicking
    };

    document.body.appendChild(playButton);
  });

  // Disable right-click context menu
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>

