---
layout: post
permalink: /landshark
title: how i made realtime "liquid" in a beer bottle in unreal
date:   2023-01-17 20:55:28 -0500 # use ctrl+alt+t to insert time or go to command palette
# the -0500 is the timezone offset for eastern time
categories: project
---

<style>
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
</style>

## Hello, this page is still a work in progress, sorry if there's missing or incomplete information!


 <video width="100%" controls autoplay loop>
  <source src="https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/landshark/good_take_loop.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

### Why I made this:

Basically, I love Half Life: Alyx. I thought the liquid-in-bottle shader they patched in a month-ish after release was super cool and I still go back to that hotel lounge area sometimes just to hang out and look at bottles. [Here, for the uninitiated](https://youtu.be/9XWxsJKpYYI?t=163)[^1]

<img src="https://cdn.vox-cdn.com/thumbor/wOs1AdQcP0Rft3t5ppjruWPZn0s=/0x0:1322x910/1200x800/filters:focal(556x350:766x560)/cdn.vox-cdn.com/uploads/chorus_image/image/66862838/half_life_alyx_booze.0.jpg" alt="Half Life: Alyx's bottle shader in action">

Before I started my internship with Steamroller Technologies this past summer, I had moved into the place I rented for the summer a week before my start date, basically right after getting done with exams. I was really, super, super excited to get started and had absolutely no work to do. It was just me alone in a city I had only previously been to for like, an hour. 

So, seeing as I was going to be spending the entire summer seated at a computer, in the interest of a healthy work-life balance, I decided to work nonstop on the computer all week building materials in unreal. 

I had sorta just learned that tech art existed, and was really bad at but also really fascinated by materials (and feel similarly now about lower level shader and graphics programming stuff - I'll get there). So I decided to try and tackle what I thought would be a crazy complex project and emulate the coolest material I could think of, the liquid-in-a-bottle from Half Life: Alyx.[^2]


### Breakdown:

For reference, I've included the graphs here as embeds from [blueprintue.com](https://blueprintue.com/), which is a super cool site where you can literally just copy and paste blueprints and materials and view and share them on the web. The only downside is that I used lots of named reroute nodes for the material to keep things tidy, and the names don't get transfered for whatever reason, so I've also uploaded images of the graph [here](/landshark_mat_images).

**Blueprint**

<div class="EmbedWrapper">
<iframe src="https://blueprintue.com/render/fy577lgl/" scrolling="no" allowfullscreen></iframe>
</div>

 **Material**

<div class="EmbedWrapper">
<iframe src="https://blueprintue.com/render/iznmevvd/" scrolling="no" allowfullscreen></iframe>
</div>

[Here's a page with screenshots of the graph.](/landshark_mat_images)

The Blueprint actor contains three meshes, and translucent outside mesh that’s shaded with the glass and beer, a not visible mesh that outputs a mask to a custom depth buffer to isolate the liquid top surface, an opaque masked inside mesh that shades the backsides of stickers (which is a separate mesh so it’s included in the opaque scene buffer and thus affected by the refraction in the translucent material). Both the outside and mask meshes have position and normal vectors set by the blueprint, and use that to mask the area above and below the liquid surface by subtracting the pixel position by the liquid surface position and taking the dot product with the liquid surface normal to get a black and white mask. The inside (flipped) mesh is assigned a custom depth stencil value, which the outside material uses to get a mask of just the liquid surface, and then uses those to shade each area separately.

The blueprint calculates the liquid surface position and rotation by calculating X and Y magnitude values that are increased when a point above the bottle’s origin changes position (the point is above the origin so rotation also changes position), and continually decreased by a factor proportional to the current magnitude for that axis, so there is a smooth falloff when the bottle stops moving and liquid comes to a state of rest. These magnitude values are multiplied by sine functions of time to combine into the X and Y elements of the up vector of the plane, so magnitude values of `0` will result in completely still surface, and values of `1` will make the liquid surface slosh back and forth vigorously.

These magnitude values are also used to interpolate between still and upset values for the foam level, foam opacity, and foam UV jiggle that are sent to the outer mesh material.

The non uniform liquid surface is calculated by taking the masks for the front and back faces of the bottle in their separate materials (both materials need to calculate a mask, only one needs to use it) using them to offset the output of three sine material functions I made that take the world X position of each pixel to calculate a Z value, offset by the mask, that creates a sine wave mask along the outer edge of the bottle to represent the surface of the liquid. The sine functions have “wave_height” attributes that are multiplied by the per-axis magnitudes added together to make the surface still when at rest, and upset when moved until the “liquid” settles. Since the two materials use the same authored values to create the look of the upset liquid, a material parameter collection referenced in the materials stores these values so they only need to be adjusted in one place.




For the liquid, since colored refractions aren’t supported in Unreal, the scene color is multiplied by the beer color

The inside mesh has a material that masks the surface of the 

Places where I failed:

Water Droplets

Particles:


Shots in reel:

Turntable shot of the bottle spinning in the center of the screen, side by side with reference

blueprint controls slide over from the right on top of reference

change fill level

move and rotate around, show water surface changing

change viscosity

change liquid color

show stencil buffer

---
{: data-content="footnotes"}

[^1]: There's also [this 2kilksphilip video](https://www.youtube.com/watch?v=8kQW2jFPYZo) that more accurately conveys how I felt playing the game, seeing these ridiculously cool bottles

[^2]: [Here's what I had at the end of that week by the way](https://www.youtube.com/watch?v=0S25k2flpcw) - most of it is there, but also only the easy parts, and even those parts poorly implemented. Also the graph was a total mess then; I'm very glad I couldn't find any screenshots of it even just to make fun of myself, because I would've, and it would've been maximum painful.
