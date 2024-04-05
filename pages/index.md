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

<h1 class="page-title">Go Kitty Go!</h1>

<div class="scroll-text">
  <span class="rainbow-text">Go kitty, go kitty
Go kitty, go, and just
Ride kitty, ride kitty
Ride kitty, roll
Go kitty, go kitty
Go kitty, go, and just
Ride kitty, ride kitty
Ride kitty, roll </span>
</div>
