---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/mm-home-page-feature.jpg
  cta_label: "<i class='fa fa-download'></i> Install Now"
  cta_url: "/docs/quick-start-guide/"
  caption:

---

# Weird.

`adjective.` suggesting something supernatural; uncanny.
{: .notice--short}
oh well it also means...

`verb.` induce a sense of disbelief or alienation in someone.
{: .notice--warning}
but lets focus on the positive aspects :)

### This is the home of some weird development stuff.

### Most noteably - TestMe IntelliJ Plugin

 <h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

 {% for post in paginator.posts %}
   {% include archive-single.html %}
 {% endfor %}

 {% include paginator.html %}
