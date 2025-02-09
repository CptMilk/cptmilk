---
layout: default
permalink: /
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
{% include landing.html %}

<style>
.page-title {
  text-align: center;
  cursor: pointer;
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

#visitor-counter {
  text-align: center;
  font-size: 1.2rem;
  color: #666;
  margin-top: 15px;
}
</style>

<h1 class="page-title">Click for a Surprise!</h1>
<div id="visitor-counter">Visitors: <span id="count">0</span></div>

<div class="overlay"></div>

<div id="videoContainer">
  <div class="video-overlay" style="position: absolute; top: 0; left: 0; width: 150%; height: 150%; z-index: 30;"></div>
  <video id="surpriseVideo" src="/sounds/Edit.mp4"></video>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    fetch('https://api.countapi.xyz/hit/cptmilk.xyz/visits')
      .then(response => response.json())
      .then(data => {
        document.getElementById('count').textContent = data.value;
      })
      .catch(error => console.error('Error:', error));
  });

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

  document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
  });

  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>
