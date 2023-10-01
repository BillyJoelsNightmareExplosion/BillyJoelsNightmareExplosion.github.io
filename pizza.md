---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
permalink: /pizza/
categories: pizza
rating: 0
---

Hello. This is the most recent pizza I've made and photographed. Please [contact me](/home) or [create an issue](https://github.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/issues) if this pizza is out of date.


<!-- liquid seems kinda cool, huh -->
{% assign ratings = site.data.pizza_ratings %}

{% assign ratingTotal = 2.0 %}
{% assign ratingCount = 0.0 %}

{% for rating in ratings %}
  {% assign ratingData = rating[1] %}
  {% assign ratingAvg = ratingAvg | plus: ratingData.rating %}
  {% assign ratingCount = forloop.length %}
{% endfor %}


<style>
html {
  background-color: white;
}
div.a {
  text-align: center;
  padding: 10px;
}
.pizza {
  background-color: darkred;
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  font-size: 25px;
  border-radius: 12px;
}
.button {
  padding: 15px 32px;
  display: inline-block;
  margin: 2px;
  cursor: pointer;
}
.bar {
  display: block;
  padding:8px 16px;
  background-color: darkred;
  width: {{ ratingAvg | divided_by: ratingCount | divided_by: 7.0 | times: 100 }}%;
  height: 16px;
}
.container {
  background-color: darkgray;
  width: 100%;
  height: 20%;
}
.name {
  background-color: white;
  border: solid;
  color: darkred;
  border-color: darkred;
  border-width: medium;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 80%;
}
</style>

{% include framed-img.html src='https://raw.githubusercontent.com/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/_files/photos/pizza/pizza.jpg' %}

<script>
function SwapDivsWithClick() {
  var x = document.getElementById("pizzaForm");
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }      
}
</script>

<div class="pizzaForm">  
  <form method="POST" action="https://ppnhpl5rh1.execute-api.us-east-2.amazonaws.com/prod/v2/entry/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/pizza_ratings">
    <input name="options[slug]" type="hidden" value="{{ page.slug }}">
    <div class="a" >
    enter your name:
    </div>
    <textarea class="pizza name" rows="1" name="fields[name]" required></textarea>
    <div class="a" >
    rate this pizza:
    </div>
    <div class="a" >
    {% for i in (1..7) %}
      <button type="submit" name="fields[rating]" value="{{ i }}" class="pizza button" onclick="SwapDivsWithClick()">{{ i }}</button>
    {% endfor %}
    </div>
  </form>
</div>

***

<br>
<div class="a" >
average rating of this pizza:
</div>

<div class="pizza container">
  <div class="pizza bar"></div>
</div>
{% include left-right.html tag='p' left='▲ terrible' right ='7 ▲' %}

> **paitience:** it will literally take in excess of a minute for your submission to be reflected on this page 🍄☮🧿🪴🍵🫂🤲🏻🧘🏼‍♀️ 
