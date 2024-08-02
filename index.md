---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
permalink: /home
---


<style>
html {
  background-color: #000026;
  background-attachment: fixed;
  background-image: linear-gradient(hsl(0, 0%, 10%), #000026, #40415c);
}

@keyframes candleFlicker {
  0%   { text-shadow: 0 4px 10px hsl(30, 100%, 80%), 0 4px 20px hsl(30, 100%, 80%), 0 4px 30px hsl(30, 100%, 80%); }
  30%  { text-shadow: 0 4px 10px hsl(30, 65%, 45%), 0 4px 20px hsl(30, 65%, 45%), 0 4px 30px hsl(30, 65%, 45%); }
  75%  { text-shadow: 0 4px 10px hsl(30, 75%, 65%), 0 4px 20px hsl(30, 75%, 65%), 0 4px 30px hsl(30, 75%, 65%); }
  80%  { text-shadow: 0 4px 10px hsl(30, 70%, 50%), 0 4px 20px hsl(30, 70%, 50%), 0 4px 30px hsl(30, 70%, 50%); }
  85%  { text-shadow: 0 4px 10px hsl(30, 70%, 30%), 0 4px 20px hsl(30, 70%, 30%), 0 4px 30px hsl(30, 70%, 30%); }
  87%  { text-shadow: 0 4px 10px hsl(30, 70%, 50%), 0 4px 20px hsl(30, 70%, 50%), 0 4px 30px hsl(30, 70%, 50%); }
  100% { text-shadow: 0 4px 10px hsl(30, 100%, 80%), 0 4px 20px hsl(30, 100%, 80%), 0 4px 30px hsl(30, 100%, 80%); }
}

h1, body {
  color: white;
}
a {
    color: lightblue;
    text-decoration: none;
}
a:visited, a:active {
    color: pink;
}
a:hover, a:focus {
    text-decoration: underline;
}
</style> 


<canvas id="c"> </canvas>

<style>
canvas {
  z-index: -10; 
  margin: 0px; 
  padding: 0px; 
  background-color: transparent; 
  text-wrap: nowrap;
  position: fixed;
  float: left;
  left: 0px;
  top: -20px;
  filter: opacity(50%);
  -webkit-mask-image: -webkit-gradient(linear, left top, 
  left bottom, from(rgba(0,0,0,0.5)), to(rgba(0,0,0,1)));
}
</style>

<script>
var rainNum = window.innerWidth * 1;

var canvas = document.getElementById('c');
var ctx = canvas.getContext('2d');

var w = window.innerWidth; var h = document.body.scrollHeight + 20;
var x = 100; var y = 100;

var rain = [];
for(i = 0; i < rainNum; i++) {
  rain.push(new newRain);
}


function getRandomArbitrary(min, max) {
  return Math.random() * (max - min) + min;
}

function newRain() {
  this.x = Math.random() * w;
  this.y = Math.random() * h;
  this.w = getRandomArbitrary(0, 1);
  this.h = getRandomArbitrary(0, 40);
}

var draw = function() {
  c.width = w;
  c.height = h;

  for(t = 0; t < rain.length; t++) {
    var r = rain[t];

    ctx.beginPath();
    ctx.fillStyle = 'white';
    ctx.fillRect(r.x, r.y, r.w, r.h);

    r.y = r.y + (0.5 * (r.h));

    if(r.y > h + 20) {
      r.y = -20;
    }
  }
};

setInterval(draw, 3);
</script>