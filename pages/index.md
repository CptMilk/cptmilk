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
  #visitor-counter {
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

<!-- Visitor counter display (integration code from our documentation) -->
<div id="visitor-counter">Loading visitor count...</div>

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

  // When the DOM is fully loaded, fetch and display the visitor counter from the API
  document.addEventListener("DOMContentLoaded", function() {
    // Replace 'YOUR_API_KEY' with your actual API key
    const apiKey = 'db212e1cd2d04ec17cc7097d96f0c1e52608b237';
    const apiUrl = 'https://api.cptmilk.xyz/visit?api_key=' + apiKey;

    fetch(apiUrl)
      .then(response => response.json())
      .then(data => {
        document.getElementById('visitor-counter').textContent = 'Visitor Count: ' + data.visitor_count;
      })
      .catch(error => {
        console.error('Error fetching visitor count:', error);
        document.getElementById('visitor-counter').textContent = 'Error loading visitor count.';
      });
    
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
});  
</script>
