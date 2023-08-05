---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
permalink: /portfolio
categories: project
redirect_from:
  - / 
---


<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
h1 {
  color: white;
}
.fa {
  border-style: groove;
  border-width: 5px;
  border-radius: 10px;
  border-color: pink;
  padding: 10px; 
  color: black;
  font-size: 22px;
  width: 20px;
  text-align: center;
  text-decoration: none;
  margin: 2px 2px;
  transform: translate(0%, -10%);
}

.fa:hover {
  opacity: 0.8;
  border-style: ridge;
  border-radius: 10px;
  padding: 8px; 
  font-size: 22px;
  color: lightblue;
  border-color: lightblue;

}

.fa-linkedin {
  font-size: 18px;
}

.fa-resume {
  width: 75px;
  font-family: 'alte_haas_groteskbold', sans-serif;
  font-size: 18px;
  margin: 2px 2px;
  min-height: 100%;
  overflow-wrap: break-word;
}

</style>

<!-- Add font awesome icons -->
<h1>
Alec Tremblay, Technical Artist
<a href="https://www.linkedin.com/in/alectremblay/" class="fa fa-linkedin"></a>
<a href="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/resume.pdf" class="fa fa-resume">resume</a>
</h1>

<style>
html, body {
  min-height: 100%;
  color: white;
  background-color: black; /* For browsers that do not support gradients */
  /* background-image: linear-gradient(#55646e, #c8c8c8 20%); */
  background-image: url('https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/portfolio/blur.png');
  background-attachment: fixed;
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
.videoWrapper {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
    overflow: hidden;
}
.videoWrapper iframe {
    position: absolute;
    border-radius: 15px;
    overflow: hidden;
    z-index: 1;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
.projectTile {
    position: relative;
    margin: 30px 0px;
    display: block;
    padding-bottom: 56%; /* 16:9 */
    clip-path: inset(0% 0% 0% 0% round 10px);
    opacity: 0.5;
    filter: grayscale(100%) sepia(100%) brightness(100%) hue-rotate(-100deg);
}
.projectTile:hover {
    opacity: 1;
    filter: sepia(0%)
}
.projectTileImage {
    position: absolute;
    border-radius: 15px;
    overflow: hidden;
    width: 100%;
    height: auto;
}
</style>

Hello! Below you'll find my reel and links to some of my work that I've highlighted. If you're interested in contacting me or browsing the rest of this site, you can go to the [/home](/home) page.

<div class="videoWrapper">
<iframe
width="640"
height="362"
src="https://www.youtube.com/embed/lVGSqY_PqnE"
color=white
title="YouTube video player"
frameborder="0"
allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

<style>
a.fill-div {
    display: block;
    height: 100%;
    width: 100%;
    text-decoration: none;
}
.projectTileLabel {
  position: absolute;
  top: 0px;
  left: 18px;
  font-size: 24px;
  text-shadow: 2px 2px 8px #000000;
  color: pink;
}
.projectTile:hover .projectTileLabel {
  color: lightblue;
}
</style>


<div class="projectTile">
<a href="/landshark" class="fill-div">
<img class="projectTileImage" src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/portfolio_button.gif" >
<h1 class="projectTileLabel">realtime "liquid" in unreal</h1>
</a>
</div>

<div class="projectTile">
<a href="https://alectrem.itch.io/doomed-tales" class="fill-div">
<img class="projectTileImage" src="https://img.itch.zone/aW1hZ2UvMjE3NTg0Mi8xMjg1Mzc4My5naWY=/794x1000/qWsqK%2F.gif" >
<h1 class="projectTileLabel">DOOMED TALES (game jam)</h1>
</a>
</div>

<div class="projectTile">
<a href="https://youtu.be/QRKCdJUPjLg" class="fill-div">
<img class="projectTileImage" src="https://i9.ytimg.com/vi_webp/QRKCdJUPjLg/maxresdefault.webp?v=64cdc444&sqp=COSGt6YG&rs=AOn4CLDmkuxeZtrzbM8WJ0_3mT4JhSjQQA" >
<h1 class="projectTileLabel">a recreation of #70 with blender and unreal</h1>
</a>
</div>


<div class="projectTile">
<a href="https://alectrem.itch.io/squirreling-away" class="fill-div">
<img class="projectTileImage" src="https://img.itch.zone/aW1hZ2UvMTk4NzcyMi8xMTY4OTQ0MS5wbmc=/794x1000/wC%2BRqc.png" >
<h1 class="projectTileLabel">Squirreling Away (game jam)</h1>
</a>
</div>

<div class="projectTile">
<a href="https://alectrem.itch.io/who-killed-thelonious" class="fill-div">
<img class="projectTileImage" src="https://img.itch.zone/aW1hZ2UvMTcyOTY2Ny8xMDE4NTYwNC5wbmc=/794x1000/lWVxVr.png" >
<h1 class="projectTileLabel">who killed thelonious (game jam)</h1>
</a>
</div>

<div class="projectTile">
<a href="https://vimeo.com/365898993" class="fill-div">
<img class="projectTileImage" src="https://i.vimeocdn.com/video/821777457-77235e8e54841902a7bd9c625ac63b2e8fdbee8520fa7b4a40d77d219b3c3a3f-d?mw=1600&mh=844&q=70" >
<h1 class="projectTileLabel">breakup melody (short film)</h1>
</a>
</div>

<div class="projectTile">
<a href="https://youtu.be/Dn0MROC39oQ" class="fill-div">
<img class="projectTileImage" src="https://i9.ytimg.com/vi_webp/Dn0MROC39oQ/maxresdefault.webp?v=5fcf0972&sqp=CIT0tqYG&rs=AOn4CLC-GQ5s8ttMFhKcuKz4SQdQYEopxg" >
<h1 class="projectTileLabel">turn up the radio (performance art music video)</h1>
</a>
</div>