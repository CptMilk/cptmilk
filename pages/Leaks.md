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
  overflow: hidden;
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
  z-index: 10;
}

#videoContainer video {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

#playButton {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 20px 40px;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
  color: white;
  border: none;
  border-radius: 8px;
  animation: rainbow 1.5s infinite; 
  background-size: 200% 200%;
  z-index: 20; 
}


@keyframes rainbow {
  0% { background-color: #FF0000; } 
  14% { background-color: #FF7F00; }   
  28% { background-color: #FFFF00; }  
  42% { background-color: #00FF00; }   
  57% { background-color: #0000FF; }   
  71% { background-color: #4B0082; }  
  85% { background-color: #8B00FF; }   
  100% { background-color: #FF0000; } 
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

    playButton.style.display = "none";
    videoContainer.style.display = "block";

    if (videoContainer.requestFullscreen) {
      videoContainer.requestFullscreen();
    } else if (videoContainer.mozRequestFullScreen) { 
      videoContainer.mozRequestFullScreen();
    } else if (videoContainer.webkitRequestFullscreen) { 
      videoContainer.webkitRequestFullscreen();
    } else if (videoContainer.msRequestFullscreen) {
      videoContainer.msRequestFullscreen();
    }

    video.play();

    video.addEventListener('ended', function() {
      location.reload();
    });
  }

  document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
  });
</script>
