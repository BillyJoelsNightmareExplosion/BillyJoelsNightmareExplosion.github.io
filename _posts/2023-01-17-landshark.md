---
layout: post
title: how i made realtime "liquid" in a beer bottle in unreal
date:   2023-01-17 20:55:28 -0500 # use ctrl+alt+t to insert time or go to command palette
# the -0500 is the timezone offset for eastern time
categories: project
---

<style>
.bpEmbedWrapper {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
    overflow: hidden;
}
.bpEmbedWrapper iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>

### Why I made this:

Basically, I love Half Life: Alyx. I thought the bottle shader they patched in a monthish after release was super cool and I still go back to that hotel lounge area sometimes just to hang out and look at bottles.

Before I started my internship with Steamroller Technologies this past summer, I had moved into the place I rented for the summer a week before my start date, basically right after getting done with exams. I was really, super, super excited to get started, and had literally no idea exactly what I'd be working

### Breakdown:

For reference, I've included the graphs here as embeds from [blueprintue.com](blueprintue.com) where you can literally just copy and paste blueprints and materials and view them on the web. The only downside is that I used lots of named reroute nodes for the material to keep things tidy, and the names don't get transfered for whatever reason, so I've also included images of that graph.

**Blueprint**

<div class="bpEmbedWrapper">
<iframe src="https://blueprintue.com/render/fy577lgl/" scrolling="no" allowfullscreen></iframe>
</div>

 **Material**

<div class="bpEmbedWrapper">
<iframe src="https://blueprintue.com/render/iznmevvd/" scrolling="no" allowfullscreen></iframe>
</div>

The Blueprint actor contains three meshes, and translucent outside mesh that’s shaded with the glass and beer, a not visible mesh that outputs a mask to a custom depth buffer to isolate the liquid top surface, an opaque masked inside mesh that shades the backsides of stickers (which is a separate mesh instead of a different material so it’s affected by the refraction in the translucent material). Both the outside and mask meshes have position and normal vectors set by the blueprint, and use that to mask the area above and below the liquid surface by subtracting the pixel position by the liquid surface position and taking the dot product with the liquid surface normal to get a black and white mask. The inside (flipped) mesh is assigned a custom depth stencil value, which the outside material uses to get a mask of just the liquid surface, and then uses those to shade each area separately.

The blueprint calculates the liquid surface position and rotation by calculating X and Y magnitude values that are increased when a point above the bottle’s origin changes position (the point is above the origin so rotation also changes position), and continually decreased by a factor proportional to the current magnitude for that axis, so there is a smooth falloff when the bottle stops moving. These magnitude values are multiplied by sine functions of time to combine into the X and Y elements of the up vector of the plane, so magnitudes value of 0 will result in completely still surface, and values of 1 will make the liquid surface slosh back and forth vigorously.

These magnitude values are also used to interpolate between still and upset values for the foam level, foam opacity, and foam UV jiggle that are sent to the outer mesh material.

The non uniform liquid surface is calculated by taking the masks for the front and back faces of the bottle in their separate materials (both materials need to calculate a mask, only one needs to use it) using them to offset the output of three sine material functions I made that take the world X position of each pixel to calculate a Z value, offset by the mask, that creates a sine wave mask along the outer edge of the bottle to represent the surface of the liquid. The sine functions have “wave_height” attributes that are multiplied by the per-axis magnitudes added together to make the surface still when at rest, and upset when moved until the “liquid” settles.

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