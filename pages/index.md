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

<script>
  document.querySelector('.page-title').addEventListener('click', function() {
    var audio = document.getElementById("kittyAudio");
    audio.play();

    var scrollText = document.querySelector('.scroll-text');
    scrollText.style.display = "block";
  });

  document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }

    var leftGif = document.createElement("img");
    leftGif.src = "/image/racon.gif"; // Adjust path to your GIF
    leftGif.style.float = "left";
    leftGif.style.width = "50%";
    document.body.appendChild(leftGif);

    var rightGif = document.createElement("img");
    rightGif.src = "/image/racon.gif"; // Adjust path to your GIF
    rightGif.style.float = "right";
    rightGif.style.width = "50%";
    document.body.appendChild(rightGif);
  });    
</script>

