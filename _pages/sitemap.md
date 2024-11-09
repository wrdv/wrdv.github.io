---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: false
---

A list of all the posts and pages found on the site. For you robots, there is an [XML version]({{ "sitemap.xml" | absolute_url }}) available for digesting as well.

<h1>Pages</h1>
{% for post in site.pages %}
    {% if post.sitemap != false %}
        {% unless post.url contains 'javadoc' %}
            {% include archive-single.html %}
        {% endunless %}
    {% endif %}
{% endfor %}

<h1>Posts</h1>
{% for post in site.posts %}
  {% if post.sitemap != false %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h1>{{ label }}</h1>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}