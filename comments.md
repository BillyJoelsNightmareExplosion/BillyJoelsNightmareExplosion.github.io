---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
permalink: /comments/
categories: 

---



<div style="text-align:center;">

leave a comment:

<form method="POST" action="https://ppnhpl5rh1.execute-api.us-east-2.amazonaws.com/prod/v2/entry/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/master/comments">

  <input name="options[redirect]" type="hidden" value="https://alectremblay.xyz">
  <!-- e.g. "2016-01-02-this-is-a-post" -->
  <input name="options[slug]" type="hidden" value="{{ page.slug }}">
  <textarea name="fields[message]"></textarea>
  <br>
  <button type="submit">comment</button>

</form>

comments others have left:
<br><br>

{% assign reviews = site.data.comments | sort %}

{% for review in reviews reversed %}
{% assign reviewData = review[1] %}


<br>
{{ reviewData.message }}
<br>
{% endfor %}

</div>