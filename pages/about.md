---
layout: page
title: About
permalink: /about/
weight: 3
---

# **About Me**

Heya! Im CptMilk, or just milk. :wave:,<br>

I'm a livery designer (professional png maker). I pride myself in being able to make the best liveries humanly possible at the fastest speed humanly possible. I have loads of experience
(4+ Years)! I can safely say that millions of people have seen my work and probably didn't know it was me. I really like making liveries, and can make them very well.

<div class="row">
{% include about/skills.html title="Skills" source=site.data.other-skills %}
</div>

<div class="row">
{% include about/timeline.html %}
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    var attribution = document.getElementById("attribution");
    if (attribution) {
        attribution.style.display = "none";
    }
});    
</script>

<link rel="shortcut icon" type="image/x-icon" href="{{ "/image/favicon.ico" | prepend: site.baseurl }}" >
