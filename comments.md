---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
permalink: /comments/
categories: 

---

<form method="POST" action="https://ppnhpl5rh1.execute-api.us-east-2.amazonaws.com/prod/v2/entry/BillyJoelsNightmareExplosion/BillyJoelsNightmareExplosion.github.io/commments/comments">
  <input name="options[redirect]" type="hidden" value="https://alectremblay.xyz">
  <!-- e.g. "2016-01-02-this-is-a-post" -->
  <input name="options[slug]" type="hidden" value="{{ page.slug }}">
  <label><textarea name="fields[message]"></textarea>Message</label>
  
  <button type="submit">Go!</button>
</form>