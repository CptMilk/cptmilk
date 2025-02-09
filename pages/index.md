---
layout: default
permalink: /
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}">
{% include landing.html %}

<style>
  .page-title {
    text-align: center;
    cursor: pointer;
  }

  /* Styling for the counter display */
  #counterDisplay {
    text-align: center;
    font-size: 1.2em;
    margin-top: 20px;
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
    z-index: 10;
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
    z-index: 20;
  }

  #videoContainer video {
    width: 100%;
    height: auto;
    pointer-events: none;
  }
</style>

<h1 class="page-title">Click for a Surprise!</h1>

<!-- Visitor counter display -->
<div id="counterDisplay">Loading counter...</div>

<div class="overlay"></div>

<div id="videoContainer">
  <div class="video-overlay" style="position: absolute; top: 0; left: 0; width: 150%; height: 150%; z-index: 30;"></div>
  <video id="surpriseVideo" src="/sounds/Edit.mp4"></video>
</div>

<script>
  // Surprise video functionality
  document.querySelector('.page-title').addEventListener('click', function() {
    var overlay = document.querySelector('.overlay');
    var videoContainer = document.getElementById("videoContainer");
    var video = document.getElementById("surpriseVideo");

    overlay.classList.add('active');

    setTimeout(function() {
      videoContainer.style.display = "block";
      video.play();
    }, 1000);

    video.addEventListener('ended', function() {
      location.reload();
    });
  });

  // When the DOM is fully loaded, fetch and display the counter
  document.addEventListener("DOMContentLoaded", function() {
    // Hide attribution element if it exists
    var attribution = document.getElementById("attribution");
    if (attribution) {
      attribution.style.display = "none";
    }

    // Fetch the counter directly from your external API
    fetch('http://node1.say.ovh:25522/counter')
      .then(function(response) {
        return response.json();
      })
      .then(function(data) {
        document.getElementById('counterDisplay').innerText = "Visitor count: " + data.count;
      })
      .catch(function(error) {
        console.error('Error fetching counter:', error);
        document.getElementById('counterDisplay').innerText = "Error loading counter";
      });
  });

  // Disable right-click context menu
  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>
