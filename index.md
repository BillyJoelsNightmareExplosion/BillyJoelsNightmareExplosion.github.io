---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
permalink: /home
---

<body style="background-color:gray;">

<style>
body {
  min-height: 100%;
  background-image: url('https://cdn.polyhaven.com/asset_img/map_previews/concrete_wall_003/concrete_wall_003_ao_1k.jpg');
  background-attachment: fixed;
  backdrop-filter: invert(90%);
  animation: pulse 120s infinite;
}
@keyframes pulse {
  0%   { backdrop-filter: contrast(100%) sepia(0%) blur(0px) hue-rotate(0deg) invert(90%); }
  33%  { backdrop-filter: contrast(102%) sepia(10%) blur(10px) hue-rotate(0deg) invert(93%); }
  66%  { backdrop-filter: contrast(102%) sepia(10%) blur(10px) hue-rotate(180deg) invert(93%); }
  100% { backdrop-filter: contrast(100%) sepia(0%) blur(0px) hue-rotate(0deg) invert(90%); }
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