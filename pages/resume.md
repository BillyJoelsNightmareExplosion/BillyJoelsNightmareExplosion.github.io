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
  margin: 0.2rem 0;
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
  margin: 0rem 0;
  color: #545454;
}
a {
  color: #519aba;
}
ul {
  display: block;
  line-height: 16px;
  list-style: "> ";
  padding-left: 1.5rem;
 }
.container {
  display: flex;
}
.container.space-around {
  justify-content: space-around;
} 
.container.space-between {  
  justify-content: space-between;
}
@media screen and (max-width: 750px) {
  .container.space-around {display: none;}
}
@media screen and (min-width: 750px) {
  .mobile-users-go-away {display: none;}
}
.fa-linkedin {
  color: white;
  background-color: #519aba;
  border-style: solid;
  border-color: #519aba;
  clip-path: inset(0% 0% 0% 0% round 4px);
}

</style>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

# Alec Tremblay

<div class="container space-around">
  <p>Tallahassee, FL</p>
  <a href="mailto:tremblayalec14@gmail.com">tremblayalec14@gmail.com</a>
  <span>
    <p class="fa fa-linkedin">  </p>
    <a href="https://www.linkedin.com/in/alectremblay/">alectremblay</a>
  </span>
  <a href="https://alectremblay.xyz/">alectremblay.xyz</a>
</div>


## Education 

{% include left-right.html tag='h3' left='(Ongoing) Florida State University' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='Bachelor’s of Science, Computer Science, Math Minor (3.5/4.0 GPA)' right='Aug 2020 - May 2024' %}


## Experience & Professional Development
{% include left-right.html tag='h3' left='PlayStation Studios Visual Arts' right='San Diego, CA' %}
{% include left-right.html tag='p' left='Technical Artist Intern' right='May 2023 - Aug 2023 (4 months, full time)' %}

- Designed and wrote tools and automations in Python for Autodesk Maya with PyQt/Pyside2 GUI, rewrote old tools to conform to modern coding standards and best practices.
- Developed a tool that replaces Maya Shelf Editor with a custom, simplified UI and automates tool deployment across several supported Maya versions by converting redundant MEL to non-redundant JSON.
- Made user-facing documentation on Confluence.

{% include left-right.html tag='h3' left='DevLUp FSU (Game Development Club)' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='President' right='August 2023 - May 2024 (10 months, part time)' %}

- Designed, organized and ran hands-on workshops on games programming, workflows, 3D art.
- Developed a club website and began use of agile tasking to organize operations.
- Hosted game jams (hackathons) and games industry recruiters to talk to members. 

{% include left-right.html tag='h3' left='Steamroller Technologies' right='Mount Dora, FL' %}
{% include left-right.html tag='p' left='Pipeline Intern' right='May 2022 - Aug 2022 (4 months, full time)' %}

- Worked in a team on designing and developing a pipeline for with Unity and Unreal Engine development in Python with workflow-specific optimizations and automations for version control with Plastic SCM, build automation with Jenkins, Agile tasking and project management with Jira.
- Made a Jira task submission tool for Slack with Slack Bolt, Slack Block Kit and Atlassian’s REST API to reduce workload for producers for developer submitted tasks - developers can submit tasks through a Slack GUI app that will be sent to their producer and created automatically with one button press to approve the task.


{% include left-right.html tag='h3' left='Florida State University – College of Motion Picture Arts' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='Virtual Production Research Intern' right='Mar 2021 - Apr 2022 (1 year 2 months, part time)' %}

- Worked on an educational VR tour of Reims Cathedral for the Oculus Quest using Unreal Engine from laser scans and reference photography - completed scan processing in Reality Capture, retopology and texture cleanup in Blender.
- Helped construct and configure LED volume for virtual production and configure livelink Mo-Sys RED camera. Operated Unreal during shoots, moving lights, changing setups, fixing other issues, etc.


## Projects

{% include left-right.html tag='a' left='[Physics-Driven Liquid Beer in Unreal Engine 5](https://alectremblay.xyz/landshark)' right='Unreal Engine 5, Blender, Photoshop' %}

- Blueprint script calculates liquid surface position/normal and “turbulence” from bottle movement and rotation, sends to material.
- Material creates masks with custom render layer and position information to shade liquid, the liquid surface, and glass differently on one mesh, with a sine material function to make the liquid surface appear non-planar.
- Foam and bubbles appear when upset and dissipate when at rest.


{% include left-right.html tag='a' left='[3x Game Jams](https://alectrem.itch.io)' right='Godot Engine(gdscript) and Unreal Engine 4(Blueprint), Git/Plastic SCM, Blender/Maya, Photoshop' %}

- Organized and produced three 3D games, each designed and produced in 48-72 hours.
- Programmed character controllers, animation state machines, random spread weapons, effects spawning.
- Made textures, materials, effects/particles, skeletal meshes and animations for characters and weapons.

{% include left-right.html tag='a' left='[Mazda RX-8 Racecar in Unreal Engine 4](https://alectremblay.xyz/rx8)' right='Unreal Engine 5, Blender, Photoshop' %}

- Made all materials, lighting setups, rendered for print with the Unreal Movie Render Queue and path traced renderer.
- Types of surfaces include matte and shiny vinyl stickers, moulded race tires, carbon fiber, cloth/polyester.
- Car uses material layers, with a decal sheet to reduce texture size while maintaining high fidelity.

{% include left-right.html tag='a' left='[Maya Procedural Snowman Creation Tool](https://devlup.org/projects/410635808345686016/view/procedural-snowman-in-maya-with-python)' right='Python, Maya.cmds API' %}

- Python Maya native UI (have built Maya Qt UI for work) allows users to set values for snowman ball sizes, "happiness" (mouth curve profile), size and number of coal buttons and create snowmen with simple materials.

{% include left-right.html tag='a' left='[My Personal Website](https://alectremblay.xyz/)' right='Jeykyll, HTML/CSS, Github Pages, AWS Lambda, Github Actions' %}

## Tools, Activities, Interests
**Languages and Tools:** Python • C++/C and Java for school projects • Autodesk Maya/MEL API • Unreal Engine materials and Blueprint • Blender • Git/Github • Plastic SCM • Jira/Confluence (and Atlassian REST API) • Reality Capture • Davinci Resolve  
**Activities and Interests:** [Pizza!](https://alectremblay.xyz/pizza/) • Espresso/Abstract Latte Art • Filmmaking, Cinematography/Photography • Racecars • Hiking • Guitar/Songwriting

*For other "selected works"/personal musings (seriously, [pizza](https://alectremblay.xyz/pizza/)), explore [my site](https://alectremblay.xyz/)!*

> if you're an employer looking at this post-application for a role, I may have sent you an edited or cut down version of this that was tailored to the role or your organization.