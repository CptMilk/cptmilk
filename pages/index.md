---
layout: default
permalink: /
---

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
{% include landing.html %}

<style>
@keyframes rainbow {
  0% { color: red; }
  20% { color: orange; }
  40% { color: yellow; }
  60% { color: green; }
  80% { color: blue; }
  100% { color: violet; }
}

.page-title {
  animation: rainbow 5s infinite; /* Change 5s to adjust speed */
  text-align: center; /* Center the text */
  cursor: pointer; /* Change cursor on hover */
}

.scroll-text {
  text-align: center; /* Center the text */
  overflow: hidden;
  white-space: nowrap;
}

.scroll-text .rainbow-text {
  display: inline-block;
  animation: scroll 10s linear infinite; /* Change 10s to adjust speed */
}

@keyframes scroll {
  0% { transform: translateX(100%); }
  100% { transform: translateX(-100%); }
}
</style>

<audio id="kittyAudio" src="/sounds/kitty.mp3"></audio> <!-- Change the path to your kitty.mp3 file -->

<h1 class="page-title" onmouseclick="playKittySound()">Go Kitty Go!</h1>

<div class="scroll-text">
  <span class="rainbow-text">Go kitty, go kitty Go kitty, go, and just Ride kitty, ride kitty Ride kitty, roll Go, 
    go, go kitty, go, just Go, go, go kitty, go, just Go, go, go kitty, go, just Go, go, go </span>
</div>

<script>
function playKittySound() {
  var audio = document.getElementById("kittyAudio");
  audio.play();
}

document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
});    
</script>
