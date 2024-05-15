---
layout: post
permalink: /vr_piano
title: making a vr piano escape room puzzle and having ChatGPT do all the work
date:   2024-05-13 09:11:17 -0500 # use ctrl+alt+t to insert time or go to command palette
# the -0500 is the timezone offset for eastern time
categories: project
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&display=swap" rel="stylesheet">

<style>
.cormorant-garamond-light-italic {
  font-family: "Cormorant Garamond", serif;
  font-weight: 200;
  font-style: italic;
}
html {
  background-color: #000026;
  background-attachment: fixed;
  background-image: linear-gradient(hsl(0, 0%, 10%), #000026, #40415c);
}
h1, h2 {
  font-family: "Cormorant Garamond", serif;
  font-size: 2rem;
  color: white;
  animation: candleFlicker 4s infinite;
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

body, a {
  color: #ffffff;
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

Since scrolling is overrated, here's the final product. It's pretty rough around the edges, as it was a side project on top of side projects on top of a semester, but I had enough fun with it and thought the output was cool enough to include here:  

(you might wanna read the rest to understand what's happening though...)

{% include youtube-embed.html src='https://www.youtube.com/embed/GaoI6Xg41M0?si=iqHOSAjqSX0aazMP' %}

## Why I Made This

During my last semester of school, one of the ongoing projects conducted by the [Seminole Innovators](https://www.innovation.fsu.edu/seminole-innovators) was a VR escape experience called "S.I.T.N.E"[^1], that was displayed along with [my game club's](https://fsu.devlup.org) work at the [Seminole Innovators' Showcase](https://www.innovation.fsu.edu/sishowcase). The idea was that teams would each build escape rooms with unique themes and puzzles, and each room would be strung together by each having players find or obtain a battery in the level to use to power an elevator to progress to the next room, collectively making a singular escape experience. Escape House? That's a better name, JACOB!  

The team I was assigned to decided on making a "Spooky Composer Room", where we had the idea of a dead classical composer who hid musical messages in letters to his lover, and players would have decode those musical motifs and play them on a piano to escape. This would have been really cool, but I was the only one who showed up to subsequent meetings to actually make the room, so all of that ended up being a bit out of scope. While I was busy with the semester and should have wisely given up like the rest of my team, I still tried to make the whole room by myself.  

So, the video above is what I made. It has a few basically arbitrary puzzles, that consist of matching the drawings of blocks (representing keys) to a sequence of notes denoted by a red letter carved on to each key (which beautifully omits any of the charming storytelling we aspired to earlier). The puzzles are to play along with the bass notes for Fur Elise and Midnight Sonata and add the leading lines; music I hoped everyone would find familiar and fun to complete.

Unfortunately, during the actual event, people found the room a little confusing, and I'm only aware of one person solving it without any help. I made the diagrams in maybe an hour or two and didn't run the design by anybody first. I thought that lining up the physical keys with the diagrams would've been obvious, but it was major point of confusion. At the very least, once players understood that idea, they seemed to be able to solve the rest of the room. I'd like to think I'd have made something more intuitive if I had more time and someone to test the room - highlighting keys or having the motif play itself to tutorialize would've been easily doable.

## ChatGPT or: How I Learned to Stop Worrying and Love the Model

*I promise an LLM didn't write this. I hope this writing will be far too choppy and informal to have been believably written by one[^2].*

Before this past semester, I was actually generally against the idea of using LLMs to code, under the false impression that they weren't as useful as they are or that they couldn't adapt to change well throughout a project, as I had seen LLMs hallucinate and repeat themselves and repeat themselves and become worse the longer a chat went and repeat themselves; not great qualities for a coworker. However, my thinking was corrected when I took an elective class called "Code Camp" that semester. The class was just Leetcode-esque problems to solve each class, alone and in teams, with -- to my memory -- around half the problems being designed for us to use LLM services like ChatGPT or Gemini.  

For example, one of the "AI allowed" problems was "make the karaoke version of a song from the original audio". Now, I already knew how this is commonly done in DAWs from my music production hobby, but knew none of the libraries for audio processing with python. So, I described what I wanted to accomplish, and ChatGPT gave me code that essentially did that, and after tweaking how much of the overlap to remove and from which frequencies, we had code we could turn in that made Katy Perry's "I Kissed A Girl" into a distant "Mmph Kmmph uhh Gmmmhm".  

Before that, I would've felt completely unconfident with the idea I could solve that problem in an hour, even with prior knowledge -- now imagine how students who learned music production, signal processing, and made a functional solution in an hour felt!  

After taking the class, I feel way more comfortable solving problems further out of my comfort zone, because as long as I understand the core mechanics of the thing that's happening, and I know the toolset being used, an LLM can use a library I don't know and explain what it's code does, so I can fix whichever part is broken or define some algorithm to solve whichever problem at hand. And, with mostly working code already in front of you, you learn way faster. It obviously won't work for everything, but it continues to surprise me how far you get. Also, with a few basic strategies, you can be a lot more effective at using LLMs to help you work. **I'll bold those in descriptions below.**

With this project, as I wanted to apply what I learned, I decided to try relying on ChatGPT as much as possible; especially because this code could exist in isolation to other's work and was only used once for something that wasn't very high stakes (could be shit). I would write prompts, and change only tiny things in the code. I already knew C#, and had worked with game engines before, but I had not worked with Unity, so I was relying on ChatGPT to know that part.

## Making a Piano That Sounds Like a Banjo in 2 and a Half Hours, Only With The Help of All of Recorded History

I started with just trying to make the one thing that would need to work for the room to work: a really simple piano. **Asking ChatGPT "make me simple piano pls" (or any other complex and somewhat abstract problem right out of the gate) will usually result in it spitting out a whole bunch of garbage, so asking for little bits of functionality at a time, as simple as possible, keeps the thread understandable.**  

In this case, my initial idea for the piano was to have a parent piano object, and children keys, and spawning them in a for loop with positions offset by loop index and a callback function to be triggered on collision to tell the piano to play that note. Even that's a little much for one chat message, so I started with this: 

> i want to make an object that spawns child objects that, when collided with, call a function on the parent object script in unity c#  
  how would i approach that and what would be a simple script to implement this?

And it spit out two simple scripts, one for a `ParentObject`:

```csharp
using UnityEngine;

public class ParentObject : MonoBehaviour
{
    public GameObject childPrefab;

    // Function to be called when collision occurs
    public void OnCollisionFunction()
    {
        Debug.Log("Collision Detected with Child Object!");
        // Do something when collision occurs
    }

    // Function to spawn child objects
    public void SpawnChildObject(Vector3 position)
    {
        Instantiate(childPrefab, position, Quaternion.identity);
    }
}
```

And one for a `ChildObject`:

```csharp
using UnityEngine;

public class ChildObject : MonoBehaviour
{
    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Player")) // Check collision with player or specific tag
        {
            // Call the function on the parent object script
            transform.parent.GetComponent<ParentObject>().OnCollisionFunction();
        }
    }
}
```

I then asked it:

> okay, could you modify the above script so that the parent object makes three of the child objects, each 10 units apart

and it added this code to the parent:

```csharp
void Start()
{
    // Spawn child objects
    for (int i = 0; i < numberOfChildren; i++)
    {
        Vector3 spawnPosition = transform.position + Vector3.right * i * distanceBetweenChildren;
        SpawnChildObject(spawnPosition);
    }
}
```

**If you add little bits each time, ChatGPT doesn't do anything drastic, and if it does, you know which bit of the code broke.**

So, after this, I asked it:

- to add each key keeping track of it's index
- for the parent to keep track of the played key indices in a list
- make the sizing dynamic via public floats used as multipliers so I could play around with what key sizes worked in VR
- and then make it offset the pitch of a piano note sound by each key's index worth of semitones.

With about two and half hours of work from the VR template project, in a completely new tool, I had this:

{% include youtube-embed.html src='https://www.youtube.com/embed/P8nM2wA2Rkc?si=dvagGHM-Emkxjso0&amp;start=7' %}

Was any of that code really that hard or complicated? No. Any kid finishing a CS degree should be able to write that... but not anywhere near as fast. All I had to do was think of how to solve the problem, and then I was done.

Also, Jacob, who managed the project, said this sounded like a banjo. Agreed! (Now it's all I can hear 😭)

## Prompt Engineer or Spaghetti Launcher?

As I kept working on it, I added more little bits. Instead of offsetting the pitch of one sound, I found a GitHub repo of all of the sounds each piano key makes, and I had ChatGPT write a python script to convert their musical notation names to the indices of key so they could easily be assigned in the loop in the start function of the constructor. This one I remember ChatGPT actually being pretty bad at, because the naming convention was a little complicated, so I basically had to write most of that by hand. **From my experience, the more edge cases you ask ChatGPT to handle, the worse it does. Ask for the core algorithms and expect to have to implement the nuances yourself.**  

I also made it so it positioned the keys differently based off of them being sharps/flats -- if mod 12 equals (whichever numbers, i forgot), then offset differently and use the other of the two prefabs for each type of key -- and dip the key down when it's played and have it return, of course.  

To make the actual puzzle logic, I made new class `PianoListener` that would just look at the end of the list of played keys every frame (obviously not performant, but remember the context) and see if it's motif (a list of key indicies) matched. If it did, it would trigger something with interface `IPuzzleAction` to do something in the game. I basically told ChatGPT to make an interface, rather than letting it decide whether or not to use one, because I already knew I wanted this to be a reusable and customizable component. **Generally, you'll probably also have to consider reusabilty and scalbilty yourself, ChatGPT is only going to solve the problem your asking it to solve, not the problems you'll anticipate that you'll have.**  

In this clip below, along with all the further changes to the piano being implemented along with a model from SketchFab, `BoxPuzzleAction` moves a box up and plays an opening sound:

{% include youtube-embed.html src='https://www.youtube.com/embed/63s5y2lU1FU?si=owLERJRIUEizQuo8&amp;start=8' %}

After that, I realized you could do effectively the same thing in reverse to make a piano player:

> write a script for a unity gameobject that has a public list of ints called keys, a public double called spacing and has a public reference to a PianoParent, and calls  playKey on the PianoParent for each of ints in keys, delayed by spacing in milliseconds

The output of which is shown below playing a version of the Fur Elise bass notes, along with an actual box for poor old `BoxPuzzleAction`:

{% include youtube-embed.html src='https://www.youtube.com/embed/3t4dmW_VvQs?si=4bmiLJtjf8XsCkKv&amp;start=3' %}

Of course, if you're familiar with that piece, that's not really how it's supposed to sound. I did add the `PianoPlayer` that plays the rest of the song after you start it later, but the pretty obvious limitations of this system are that it didn't support chords, variable note lengths or rests; it just plays notes in equal intervals.  

Because this whole project was a big dumb hack anyways, for Moonlight Sonata, I just made it so the bass chords are just two players started on the same frame to get around that first limitation, and for the final lead note, I just added code that allowed the note index in a motif to be -1, where the player would just do nothing. If you set the note length to some multiple of the tempo for the rest of the piece, and filled in with -1s, you could have some more granular note placement.  

Did I perhaps invent the worst musical notation format of all time? Even if I somehow didn't, it certainly felt that way the entire time, because I had to transcribe all of the music manually! I spent a lot of time printing out midi note values and staring at piano roll videos and adding ints to lists, to the point where I think it wouldn't have been much harder to just build a really simple midi player.  

## Machine Learning, Human Learned

And that's where I think I messed up: even though the initial conceit of this project was that I could make bad code as long as it worked, I think LLM reliant coding inadvertently encourages this, or at least it does for me. You just let the model write the implementation, not care if it writes something verbose or repetitive or repetitive or repetitive, and then realize you messed up when have to sew all of that together. That's totally not an LLM problem, that's just a poor design problem! That's the human's fault! The human needs to do better! I think that, when I'm writing code by hand, I get frustrated when I'm writing something that feels stupid, so I go and figure out how to do it better, that learning makes the work easier and makes me a better programmer.  

**I'll argue that LLMs can teach you libraries, and they can show you how to solve problems, but they don't make you a better problem solver or a better programmer. They can really only leverage abilities you already have. When you use an LLM, you're not practicing, you're coaching. My intuition, should you choose to value it, is that if you lean too heavily on LLMs, you'll forget the nuances and stop growing as a developer.**

So, I think that, my takeaway from this project was: yeah, I'll let the LLMs handle simple stuff. And I wouldn't have had the time to make this without it! But, as a consequence of that, I need to keep growing my skill set, keep working in different domains, and do so by hand to stay sharp.  

And stop throwing spaghetti at the wall. That ought to help.

<style>
.button {
  border-style: solid;
  display: block;
  margin-left: auto;
  margin-right: auto;
  border-width: 3px;
  border-radius: 10px;
  border-color: white;
  padding: 10px; 
  margin-top: 50px;
  margin-bottom: 50px;
  color: white;
  text-shadow: 0 0 10px #6e70a3, 0 0 10px #6e70a3,0 0 10px #6e70a3,0 0 10px #6e70a3, 0 0 50px #6e70a3;
  box-shadow:  0 0 10px #6e70a3, 0 0 10px #6e70a3, 0 0 50px #6e70a3;
  background-color: transparent;
  font-size: 22px;
  text-align: center;
  transform: scale(90%);
  transition: opacity 0.2s, transform 0.2s;
}
</style>

{% assign press_count = 0 %}
{% assign presses = site.data.button_presses %}
{% for press in presses %}
{% assign pressData = press[1] %}
  {% if pressData.post_id == "vr_piano" %}
    {% assign press_count = press_count | plus: 1 %}
  {% endif %}
{% endfor %}

{% assign times = "Times" %}
{% if press_count == 1 %}
  {% assign times = "Time" %}
{% endif %}

<form method="POST" action="https://ppnhpl5rh1.execute-api.us-east-2.amazonaws.com/prod/v2/entry/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/button_presses">
  <input name="options[slug]" type="hidden" value="{{ page.slug }}">
  <input type="hidden" name="options[redirect]" value="https://alectremblay.xyz/i_pressed_the_button">
  <button  name="fields[post_id]" value="vr_piano" class="button">This Button Has Been Pressed {{ press_count }} {{ times }}</button>
</form>


---
{: data-content="footnotes"}

[^1]: Which, JACOB, stands for "SEMINOLE INNOVATORS TRY N' ESCAPE". WE GET IT. Starting every meeting with a call and response is not a form of team building, it's inciting riot. This footnote is a form of protest. Anyways love you boo thanks for reading.

[^2]: You know how filmmakers tried as hard as possible to get rid of halation and film grain and camera shake, and then when they got really good at that, threw it all back in? Or how we got really good at making photoreal real-time graphics, so now we're making boomer shooters and pixel art? I wonder if human written words will tend more towards the loose and filled with slang in the future - stuff that feels explicitly not manufacturable, with a baked-in sense of cultural perspective and handmade-ness that's hard to replicate via machine (albeit probably not impossible). For better or worse, and regardless of that outcome, I think that's what the writing will be like here :/

<html>
<!-- 

In the spirit of originality, below is code I stole and kitbashed to make this rain effect.

Rain: https://stackoverflow.com/questions/21347158/rain-effect-in-webpage
https://redeando.blogspot.com/2013/02/lluvia-en-tu-blog.html

Lerp function: https://thinkingbox.medium.com/6-simple-js-math-functions-you-can-use-everyday-68f8d5b58514

Gradient Mask: https://stackoverflow.com/questions/15597167/css-opacity-gradient

-->

<canvas id="c"> </canvas>
</html>

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
var rainNum = window.innerWidth * 1.5;

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
}

var draw = function() {
  c.width = w;
  c.height = h;

  for(t = 0; t < rain.length; t++) {
    var r = rain[t];

    ctx.beginPath();
    ctx.fillStyle = 'white';
    ctx.fillRect(r.x, r.y, getRandomArbitrary(0, 1), getRandomArbitrary(0, 40));

    r.y = r.y + (10 * Math.random());

    if(r.y > h + 20) {
      r.y = -20;
    }
  }
};

setInterval(draw, 3);
</script>
