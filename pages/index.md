---
layout: default
permalink: /
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
{% include landing.html %}

<style>
@keyframes rainbow {
  0% { color: red; }
  16.67% { color: orange; }
  33.33% { color: yellow; }
  50% { color: green; }
  66.67% { color: blue; }
  83.33% { color: indigo; }
  100% { color: violet; }
}

.page-title {
  animation: rainbow 5s infinite; /* Adjust speed as needed */
  text-align: center; /* Center the text */
  cursor: pointer; /* Change cursor on hover */
  background: linear-gradient(90deg, red, orange, yellow, green, blue, indigo, violet);
  -webkit-background-clip: text;
  color: transparent;
  background-size: 200% 100%;
  animation: gradientMove 5s infinite linear;
}

@keyframes gradientMove {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}

.scroll-text {
  text-align: center; /* Center the text */
  overflow: hidden;
  white-space: nowrap;
}

.scroll-text .rainbow-text {
  display: inline-block;
  animation: scroll 10s linear infinite; /* Adjust duration as needed */
}

@keyframes scroll {
  0% { transform: translateX(100%); }
  100% { transform: translateX(-100%); }
}

.gif-container {
  display: none;
}

.gif-container img {
  display: block;
  margin: 0 auto;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  pointer-events: none;
  background: linear-gradient(90deg, red, orange, yellow, green, blue, indigo, violet);
  background-size: 200% 100%;
  animation: none; /* No animation initially */
}

.overlay.active {
  animation: overlay-animation 5s infinite linear;
}

@keyframes overlay-animation {
  0% { background-position: 0% 50%; opacity: 0; }
  50% { opacity: 0.5; }
  100% { background-position: 100% 50%; opacity: 0; }
}
</style>

<audio id="kittyAudio" src="/sounds/pedro.mp3"></audio> <!-- Change the path to your kitty.mp3 file -->

<h1 class="page-title">Click for a Surprise!</h1>

<div class="scroll-text" style="display: none;">
  <span class="rainbow-text">Pedro, Pedro, Pedro, Pedro, Pé! Pedro, Pedro, Pedro, Pedro, Pé! Pedro, Pedro, Pedro, Pedro, Pé! Pedro, Pedro, Pedro, Pedro, Pé! Pedro, Pedro, Pedro, Pedro, Pé! </span>
</div>

<div class="gif-container">
  <img src="/image/racon.gif" style="float: left; width: 50%;" alt="Left Gif">
  <img src="/image/racon.gif" style="float: right; width: 50%;" alt="Right Gif">
</div>

<div class="overlay"></div>

<script>
  document.querySelector('.page-title').addEventListener('click', function() {
    var audio = document.getElementById("kittyAudio");
    audio.play();

    var scrollText = document.querySelector('.scroll-text');
    scrollText.style.display = "block";

    var gifContainer = document.querySelector('.gif-container');
    gifContainer.style.display = "block";

    var overlay = document.querySelector('.overlay');
    overlay.style.pointerEvents = "auto"; // Enable pointer events to allow clicking
    overlay.classList.add('active'); // Add 'active' class to show the overlay
  });

  document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
  });    
</script>

