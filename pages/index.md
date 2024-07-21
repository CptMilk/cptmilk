---
layout: default
permalink: /
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
{% include landing.html %}

<style>
.page-title {
  text-align: center; /* Center the text */
  cursor: pointer; /* Change cursor on hover */
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: black;
  opacity: 0;
  pointer-events: none;
  transition: opacity 1s;
  z-index: 10; /* Ensure the overlay is on top */
}

.overlay.active {
  opacity: 1;
  pointer-events: auto;
}

#videoContainer {
  display: none;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 20; /* Ensure the video is on top */
}

#videoContainer video {
  width: 100%;
  height: auto;
}
</style>

<h1 class="page-title">Click for a Surprise!</h1>

<div class="overlay"></div>

<div id="videoContainer">
  <video id="surpriseVideo" src="/sounds/Edit.mp4"></video>
</div>

<script>
  document.querySelector('.page-title').addEventListener('click', function() {
    var overlay = document.querySelector('.overlay');
    var videoContainer = document.getElementById("videoContainer");
    var video = document.getElementById("surpriseVideo");

    // Fade to black
    overlay.classList.add('active');

    // Wait for the fade effect to complete before starting the video
    setTimeout(function() {
      videoContainer.style.display = "block";
      video.play();
    }, 1000); // Match this to the transition duration

    // Refresh the page when the video ends
    video.addEventListener('ended', function() {
      location.reload();
    });
  });

  document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
  });    
</script>
