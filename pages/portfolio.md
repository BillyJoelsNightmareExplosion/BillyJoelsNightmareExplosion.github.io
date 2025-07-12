---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
permalink: /portfolio
categories: project
---


<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
h1 {
  color: white;
}
.fa {
  border-style: solid;
  border-width: 3px;
  border-radius: 10px;
  border-color: pink;
  padding: 10px; 
  color: black;
  font-size: 22px;
  width: 20px;
  text-align: center;
  text-decoration: none;
  margin: 2px 2px;
  transform: scale(90%);
  transition: opacity 0.2s, transform 0.2s;
}

.fa:hover {
  opacity: 0.8;
  transform: scale(100%);
  color: lightblue;
  border-color: lightblue;

}

.fa-linkedin {

}

.fa-resume {
  width: 75px;
  font-family: 'alte_haas_groteskbold', sans-serif;

  margin: 2px 2px;
  min-height: 100%;
  overflow-wrap: break-word;
}
</style> 


<h1 style="display: flex; align-items: center; font-weight: normal;">
  Alec Tremblay's Portfolio
  <a href="https://www.linkedin.com/in/alectremblay/" class="fa fa-linkedin" style="margin-left: 10px" ></a>
  <a href="/resume" class="fa fa-resume">resume</a>
</h1>

<div class="gradient-overlay"></div>

<style>
html, body {
  min-height: 100%;
  color: white;
  /* For browsers that do not support gradients */
  /* background-image: linear-gradient(#55646e, #c8c8c8 20%);  url('https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/blur.png'), */
  background-image: url('https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/film-grain.gif'), url('https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/blur_blur.png');
  background-blend-mode: overlay;
  background-attachment: fixed, fixed;
  background-size: 1400px, cover;
  background-position: center center; 

}
.gradient-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: radial-gradient(circle, rgba(255, 255, 255, 0.7), rgba(0, 0, 0, 0.5));
    mix-blend-mode: overlay;
    pointer-events: none;
}
h1 {
  color: white;
  padding: 20;
}
h2 {
  text-align: center;
}
.myLinks{
  text-align: justify;
  color: white;
}
.myLinks:after { /* Justify last line */
    content: '';
    display: inline-block;
    width: 100%; 
}
table {
  border: 1px solid transparent;
  width: 100%;
}
a:link {
  color: pink;
  background-color: transparent;
}
a:visited {
  color: pink;
  background-color: transparent; 
}
a:hover { 
  background-color: transparent;
  color: lightblue;
}
a:active {
  color: pink;
  background-color: transparent;
}
</style>

{% include portfolio-tile-style.html %}

Hello! 

Below you'll find my reel and links to some of my work that I've highlighted. If you're interested in contacting me or browsing the rest of this site, you can go to the [/home](/home) page.

Thanks for stopping by!
<meta name="viewport" content="width=device-width, initial-scale=1.0">

---

<div>

<div class="pj">
<img class="projectTileFileGate" src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/film-gate.png" style="width:auto;">
<h1 class="projectTileFilmText">KODAK</h1>
{% include youtube-embed.html src='https://www.youtube.com/embed/niuYDPQT0vs' %}
</div>

{% for tile in site.data.tiles limit:4 %}
  {% include portfolio-tile.html film-text=tile.film-text label=tile.label href=tile.href img-src=tile.img-src %}
{% endfor %}

<!-- this tile uses an iframe instead of an image, and thus requires it's own unique definition below:  -->

<div class="pj">
<img class="projectTileFileGate" src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/film-gate.png" style="width:auto;">
<h1 class="projectTileFilmText"></h1>
<h1 class="projectTileFilmText"></h1>
<div class="projectTile">
<a href="/project/2023/01/17/website.html" class="fill-div">
<iframe class="projectTileImage" src="/home" style="border:none;height:362px;scrollbar-width:none;  pointer-events: none;" ></iframe>
<img src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/1x1.png" style="width:100%;position:absolute">
<h1 class="projectTileLabel">this website</h1>
<i class="fa fa-external-link-square"></i>
</a>
</div>
</div>

<div class="pj">
<img class="projectTileFileGate" src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/film-gate.png" style="width:auto;">
<h1 class="projectTileFilmText"> EI 200/24*</h1>
<h1 class="projectTileFilmText"></h1>
<div class="projectTile">
<a href="https://fsu.devlup.org/posts/gbm-1-f23" class="fill-div">
<iframe class="projectTileImage" src="https://fsu.devlup.org/posts/gbm-1-f23" style="border:none;height:362px;scrollbar-width:none;  pointer-events: none;" ></iframe>
<img src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/1x1.png" style="width:100%;position:absolute">
<h1 class="projectTileLabel">DevLUp FSU website (my game dev club)</h1>
<i class="fa fa-external-link-square"></i>
</a>
</div>
</div>


{% for tile in site.data.tiles offset:4 %}
  {% include portfolio-tile.html film-text=tile.film-text label=tile.label href=tile.href img-src=tile.img-src %}
{% endfor %}