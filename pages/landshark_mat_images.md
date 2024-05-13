---
layout: page
permalink: /landshark_mat_images
title: how i made realtime "liquid" in a beer bottle in unreal
date:   2023-01-17 20:55:28 -0500 # use ctrl+alt+t to insert time or go to command palette
# the -0500 is the timezone offset for eastern time
categories: project
---


<style>
html {
  background-color: #242424;
}
body, h1, a {
  color: #ababa9;
  filter: drop-shadow(#0d0d0c 0rem 0rem 10px);
}
.EmbedWrapper {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
    overflow: hidden;
}
.EmbedWrapper iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
img, .EmbedWrapper, video {
    clip-path: inset(0% 0% 0% 0% round 10px);
    margin-top: 2rem;
    margin-bottom: 2rem;
 }
</style>

[back to the project page](/landshark)

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/fill_mask.png "fill_mask.png")

This graph takes the plane position and normal set by the blueprint each tick and makes a mask for liquid below the surface offset by the three sine offset material functions I made and also makes a mask for the walls foam lining the inside walls of the bottle.

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/foam.png "foam.png")

This graph outputs the color of the foam in the bottle using two different sets of UVs for shading the foam against the side of the bottle and the top surface of the liquid using a cool way to calculate the UVs for a surface described by an up-vector I found [here]()

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/glass_thickness_mask.png "glass_thickness_mask.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/intersection_mask.png "intersection_mask.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/label.png "label.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/liquid_shading.png "liquid_shading.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/output.png "output.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/scene_distortion_uv.png "scene_distortion_uv.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/base_color.png "base_color.png")

---

![Alt Text](https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/graphs/camera_space_bottle.png "camera_space_bottle.png")

