---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
permalink: /resume
categories:
---

<style>

@import url('https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible&display=swap');

 .w {
    font-family: 'Atkinson Hyperlegible', monospace;
    max-width: 100%;
    margin-bottom: 0;
    padding: 1rem 2rem;
 }
 h1, blockquote {
   text-align: center;
 }
  h2 {
   border-bottom: 2px ridge;
   width: 100%;
   display: block;
   margin: 0.5rem 0;
 }
h3 {
  margin: 0.1rem 0;
  line-height: 1rem;
}
p, ul {
  margin: 0.2rem 0;
  color: #545454;
}
 ul {
   list-style: "> ";
   padding-left: 1.5rem;
 }
.myLinks { /* thanks old bad portfolio page! */
  margin: 0.2rem 0;
  color: #545454;
  text-align: justify;
  color: black;
}
.myLinks:after { /* Justify last line */
    content: '';
    display: inline-block;
    width: 100%;
}
</style>

# Alec Tremblay

<div class="myLinks">
<a href="mailto:tremblayalec14@gmail.com">tremblayalec14@gmail.com</a>
<a href="https://www.linkedin.com/in/alectremblay/">linkedin.com/in/alectremblay</a>
<a href="https://alectremblay.xyz/">alectremblay.xyz</a>
<a>(954)-850-6057</a>
</div>

## Experience 
### Technical Artist Intern - PlayStation Studios Visual Arts
May 2023 - Aug 2023 (4 months, full time)  
- Designed and wrote tools and automations in Python for Autodesk Maya with PyQt/Pyside2 GUI, as well as rewrote old tools to conform to modern coding standards and best practices. Made user-facing documentation on Confluence.

### Pipeline Intern - Steamroller Technologies  
May 2022 - Aug 2022 (4 months, full time) 
- Worked in a team on planning, developing a pipeline for game and themed experience development in Python with workflow-specific optimizations and automations for version control with Plastic, continuous integration with Jenkins, Agile task tracking and project management with Jira for use with Unity and Unreal Engine development.
- Made a Jira task submission tool for Slack with Slack Bolt, Slack Block Kit and Atlassian’s REST API to reduce workload for production for developer submitted tasks. Developers can submit tasks through a Slack GUI app that will be DM’d to their production coordinator and created automatically with one button press to approve the task.
- Built developer-facing documentation for my code with Doxygen and user-facing documentation on Confluence.

### Virtual Production Research Intern - Florida State University  
Mar 2021 - Apr 2022 (1 year 2 months, part time)  
- Completed scan processing in Reality Capture, mesh retopology and texture cleanup in Blender, layout and final construction of Reims cathedral for an educational VR tour for the Oculus Quest using Unreal Engine.
- Helped construct and configure LED wall stage for virtual production and configure livelink Mo-Sys RED camera. Operated Unreal during shoots, moving lights, changing setups, fixing other issues, etc.
- Made Python code contributions to CG Lumberjack pipeline tools for Unreal Engine.

## Professional Development
### President - DevLUp FSU (Game Development Club)
August 2023 - May 2024  
- Designed, organized and ran hands-on workshops on games programming, workflows, 3D art.
- Grew organization from ~5 attendees per meeting to ~30
- Developed a club website and began use of agile tasking to organize operations.
- Hosted game jams (hackathons) and games industry recruiters to talk to members. 

## Projects
### [Dynamic Beer Shader in Unreal Engine 5](https://alectremblay.xyz/landshark)
Unreal Engine 5, Blender, Photoshop
- Blueprint script that calculates liquid surface position/normal and "turbulence" from movement and rotation, sends to material
- Material creates masks with custom render layer and position information to shade liquid, the liquid surface, and glass differently on one mesh
- Custom sine material function multiples wave height by turbulence to offset masks for an uneven liquid surface
- Foam and bubbles appear when upset and dissipate when at rest  

### [DOOMed Tales (game jam)](https://alectrem.itch.io/doomed-tales)
Godot Engine (gdscript), Git, Blender/Maya, Photoshop  
- Implemented character controller, shotgun with random spread and animations, spline based ziplines
- Made textures, materials, post-processing, particles
- Organized game jam and managed project

### [Mazda RX-8 Racecar in Unreal Engine 4](https://alectremblay.xyz/rx8)
Unreal Engine 5, Blender, Photoshop  
- Rendered in Unreal Engine 4, made all materials, lighting setups.
- Types of surfaces include matte and shiny vinyl stickers, moulded race tires, carbon fiber, cloth/polyester
- Car body material uses material layers, with a decal sheet to reduce texture size while maintaining high fidelity.

### Snowman Tool? Some other kind of tool
Python, Maya.cmds API
- Python Maya native UI (have built Maya Qt UI for work) allows users to set values for snowman ball sizes, "happiness" (mouth curve profile), size and number of coal buttons and create snowmen
- Creates polySpheres in the scene with correct transforms and radii, builds simple materials and assigns them

### [My Personal Website](https://alectremblay.xyz/)
Jeykyll, Html/Css


## Education 
### (Ongoing) Florida State University  
Bachelor's of Science, Computer Science, Math Minor (3.5/4.0 GPA)  
Graduating May 2024

## Tools 
Python  •  Autodesk Maya/MEL API • Unreal Engine materials and Blueprint • Blender • Plastic SCM  • Git • Jira/Confluence • Reality Capture • C++/Java for school projects  

*For hobbies/interests/personal musings on things (like pizza), explore my site!*

> if you're an employer looking at this post-application for a role, I may have sent you an edited or cut down version of this that was tailored to the role or your organization.