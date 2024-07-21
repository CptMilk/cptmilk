---
layout: default
title: Game Leaks
permalink: /leaks
weight: 3
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
  background: black; /* Black background for better visibility */
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
  document.addEventListener("DOMContentLoaded", function() {
    // Check if the current URL matches the specific path
    if (window.location.pathname === '/leaks') {
      var videoContainer = document.getElementById("videoContainer");
      var video = document.getElementById("surpriseVideo");

      // Display the video container
      videoContainer.style.display = "block";

      // Request full screen
      videoContainer.requestFullscreen().then(() => {
        // Play the video
        video.play();

        // Refresh the page when the video ends
        video.addEventListener('ended', function() {
          location.reload();
        });
      }).catch(err => {
        console.log(`Error attempting to enable full-screen mode: ${err.message} (${err.name})`);
      });
    }
  });

  // Disable right-click context menu
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>
