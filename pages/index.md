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
  animation: scroll 120s linear infinite; /* Adjust duration to 120s */
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
  background: linear-gradient(to right, red, orange, yellow, green, blue, violet);
  opacity: 0;
  pointer-events: none;
  animation: overlay-animation 5s infinite alternate; /* Adjust speed as needed */
}

@keyframes overlay-animation {
  0% { opacity: 0; }
  100% { opacity: 0.5; } /* Adjust opacity level */
}
</style>

<audio id="kittyAudio" src="/sounds/pedro.mp3"></audio> <!-- Change the path to your kitty.mp3 file -->

<h1 class="page-title">Click for a Surprise!</h1>

<div class="scroll-text" style="display: none;">
  <span class="rainbow-text">Passeggio tutta sola
Per le strade
Guardando attentamente
I monumenti
La classica straniera
Con un'aria strana
Che gira stanca
Tutta la città
A un certo punto
Della passeggiata
Mi chiama da una parte
Un ragazzino
Sembrava a prima vista
Tanto per benino
Si offre a far da guida
Per la città
Pedro, Pedro, Pedro, Pedro, Pe
Praticamente il meglio
Di Santa Fe
Pedro, Pedro, Pedro, Pedro, Pe
Fidati di me
Altro che ragazzino
Che per benino
Sapeva molte cose
Più di me
Mi ha portato tante volte
A veder le stelle
Ma non ho visto niente
Di Santa Fe
Pedro, Pedro, Pedro, Pedro, Pedro, Pe
Praticamente il meglio
Di Santa Fe
Pedro, Pedro, Pedro, Pedro, Pe
Fidati di me
Mi sono innamorata
Seduta stante
Di Pedro, Pedro, Pedro
Di Santa Fe
Mi ha sconvolto le vacanze
Mi ha stregata
Non faccio che pensare
A Pedro Pe
Pedro, Pedro, Pedro, Pedro, Pedro, Pe
Travolta di passione a Santa Fe
Pedro, Pedro, Pedro, Pedro, Pe
Tornerò da te
Come ballava bene sotto le stelle
Praticamente il meglio di Santa Fe
Le ragazze lo mangiavano
Con lo sguardo
Ma lui si concentrava solo con me
Pedro, Pedro, Pedro, Pedro, Pedro, Pe
Bellissima avventura di Santa Fe
Pedro, Pedro, Pedro, Pedro, Pe
Soli io e te
Mi sono innamorata
Seduta stante
Di Pedro, Pedro, Pedro
Di Santa Fe
Mi ha sconvolto le vacanze
Mi ha stregata
Non faccio che pensare
A Pedro Pe
Pedro, Pedro, Pedro, Pedro, Pedro, Pe
Praticamente il meglio di Santa Fe
Pedro, Pedro, Pedro, Pedro, Pe
Tornerò da te</span>
</div>

<div class="gif-container">
  <img src="/path/to/racon.gif" style="float: left; width: 50%;" alt="Left Gif">
  <img src="/path/to/racon.gif" style="float: right; width: 50%;" alt="Right Gif">
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
  });

  document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
  });    
</script>

