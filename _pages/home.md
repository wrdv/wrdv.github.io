---
layout: splash
permalink: /
header:
  overlay_color: "#ffffff"
  overlay_image: /assets/images/mm-home-page-creampaper.png
word: Weird.
---

{:.handy.bigger}
This is home for some weird development stuff.
 
 <h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

 {% for post in paginator.posts %}
   {% include archive-single.html %}
 {% endfor %}

 {% include paginator.html %}
