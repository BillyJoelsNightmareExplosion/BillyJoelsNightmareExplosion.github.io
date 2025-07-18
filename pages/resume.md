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
  width: 65rem;
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
  list-style: "- ";
  padding-left: 1.5rem;
 }
.links-for-desktop {
  display: flex;
  justify-content: space-around;
}
@media screen and (max-width: 70rem) {
  .w {width: 90%;}
}
@media screen and (max-width: 750px) {
  .links-for-desktop {display: none;}
}
@media screen and (min-width: 750px) {
  .links-for-mobile {display: none;}
}
@media print
{   
    .w
    {
      width: 92%;
    }
    .no-print, .no-print *
    {
        display: none !important;
    }
}
.fa-linkedin {
  color: white;
  background-color: #519aba;
  border-style: solid;
  border-color: #519aba;
  clip-path: inset(0% 0% 0% 0% round 4px);
}
{% include left-right-style.css %}
</style>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

# Alec Tremblay

<div class="links-for-desktop">
    <p>(954)-850-6057</p>

    <a href="mailto:tremblayalec14@gmail.com">tremblayalec14@gmail.com</a>
  <span>
    <p class="fa fa-linkedin">  </p>
    <a href="https://www.linkedin.com/in/alectremblay/">alectremblay</a>
  </span>
</div>


<div class="links-for-mobile no-print" style="text-align:center; line-height:2rem;">
  <a href="mailto:tremblayalec14@gmail.com">tremblayalec14@gmail.com</a>
  <br>
  <span>
    <p class="fa fa-linkedin">  </p>
    <a href="https://www.linkedin.com/in/alectremblay/">alectremblay</a>
  </span>
  <br>
  <a href="https://alectremblay.com/">alectremblay.com</a>
</div>


## Experience & Professional Development
{% include left-right.html tag='h3' left='Cognizant' right='Remote' %}
{% include left-right.html tag='p' left='Associate Consultant (Cognizant Workday Practice)' right='Jul 2025 - Present' %}

- I just started but I'll let you know in a bit! (Very excited if you're curious!)

{% include left-right.html tag='h3' left='Sony Interactive Entertainment' right='San Diego, CA' %}
{% include left-right.html tag='p' left='Software Engineering Intern (Tools and Pipeline Developer)' right='May 2023 - Aug 2023' %}

- Programmed pipeline and tools in Python for Autodesk Maya with PyQt/Pyside2 GUI.
- Rewrote old tools to conform to modern coding standards and best practices.
- Designed a tool that replaces Maya Shelf Editor with a custom UI and pipelines tool deployment across several supported Maya versions.
- Authored comprehensive user-facing documentation and tutorials on Confluence.

{% include left-right.html tag='h3' left='Steamroller Technologies' right='Mount Dora, FL' %}
{% include left-right.html tag='p' left='Pipeline Developer Intern' right='May 2022 - Aug 2022' %}

- Worked on designing and developing a pipeline for Unity and Unreal Engine in Python, version control with Plastic SCM, CI/CD with Jenkins, Agile tasking and project management with Jira.
- Developed a Jira task submission UI in Slack with Slack Bolt and Atlassian’s REST API. Developers can submit tasks through Slack that will be sent to their producer and created automatically with one button press to approve the task.

{% include left-right.html tag='h3' left='College of Motion Picture Arts, Florida State University' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='Virtual Production Research Intern' right='Mar 2021 - Apr 2022' %}

- Developed a VR tour of Reims Cathedral for Oculus Quest in Unreal Engine from laser scans and reference photography - completed scan processing in Reality Capture, retopology and texture cleanup in Blender.
- Helped start FSU's virtual production program, by constructing and configuring an LED volume for virtual production and real-time motion tracked RED camera. Operated Unreal during shoots, virtually moving lights, changing setups, troubleshooting, etc.

{% include left-right.html tag='h3' left='FSU Game Development Club (DevLUp FSU)' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='President' right='Aug 2023 - May 2024' %}

- Designed, organized and taught dozens of weekly hands-on workshops on programming, math, 3D art and animation.
- Created a club website and grew attendance with blog posts, Discord and Instagram.
- Hosted game jams (hackathons) and games industry recruiters from Epic Games and PlayStation. 
- This experience is old and irrelevant enough that I should kick it off but I'm really proud of the work we did and I'm proud of my friends, so it stays.

## Education 

{% include left-right.html tag='h3' left='Florida State University' right='Tallahassee, FL' %}
{% include left-right.html tag='p' left='BS, Computer Science, Minor in Mathematics (3.5 GPA)' right='May 2024' %}


## Projects

{% include left-right.html tag='a' left='[Physics-Driven Liquid Beer in Unreal Engine 5](https://alectremblay.com/landshark)' right='Unreal Engine 5, Blender, Photoshop' %}

- Blueprint script calculates liquid surface position/normal and “turbulence” from bottle movement and rotation, sends to material.
- Material creates masks with custom render layer and position information to shade liquid, the liquid surface, and glass differently on one mesh, with a sine material function to make the liquid surface appear non-planar.
- Foam and bubbles appear when upset and dissipate when at rest.


{% include left-right.html tag='a' left='[5x Game Jams (Production, Development)](https://alectrem.itch.io)' right='Godot Engine(gdscript) and Unreal Engine 4(Blueprint), Git/Plastic SCM, Blender/Maya, Photoshop' %}

- Coordinated production for five 3D games, each designed and produced in 48-72 hours.
- Programmed character controllers, animation state machines, random spread weapons, effects spawning and more.
- Made textures, materials, effects/particles, models, skeletal animations, and music in various styles.

{% include left-right.html tag='a' left='[Maya Procedural Snowman Creation Tool](https://devlup.org/projects/410635808345686016/view/procedural-snowman-in-maya-with-python)' right='Python, Maya.cmds API' %}

- Python Maya native UI (have built Maya Qt UI for work) allows users to set values for snowman ball sizes, "happiness" (mouth curve profile), size and number of coal buttons and create snowmen with simple materials.

{% include left-right.html tag='a' left='["Latte Rorschach Test" Website](https://github.com/Dominic-Miller/Latte-Rorschach)' right='Python, Django, HTML5/CSS, SQLite3' %}

- Developed a web application using Django in a team, designing and implementing the front-end with HTML/CSS.
- Defined server-side data structures and admin interface configuration for user content.
- Implemented database actions handling user submissions.

{% include left-right.html tag='a' left='[My Personal Website](https://alectremblay.com/)' right='Jeykyll, HTML5/CSS, JavaScript, Github Pages, AWS Lambda, Github Actions' %}

## Skills, Languages, Tools
**Skills:** Software Engineering • Pipeline Design and Development/DevOps • 3D Modeling • Agile Development • Documentation • Requirements Analysis/Design  
**Languages:** : C++/C • C# (Unity, .NET Maui with XML) • Java • Python (Django, PySide2, MatPlotLib) • JSON • HTML5 • Perl • SQL  
**Tools:** Unix/Linux (Kernel Modules, Shell Scripting) • Unreal Engine • Blender • Jira/Confluence • Photoshop • Autodesk Maya • Unity •
Godot • Git/Github • AWS (EC2, Lambda) • Jenkins  
**Hobbies & Interests:** Guitar/Music Production/Songwriting • Espresso/Latte Art • Trail Running • Film/Photography • Cooking/[Pizza](https://alectremblay.com/pizza) • [Racecars](https://alectremblay.com/rx8)