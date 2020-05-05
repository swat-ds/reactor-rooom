---
layout: single
author_profile: false
classes: ['splash']
header:
  overlay_filter: "rgba(100,100,100,.5)"
  overlay_image: /assets/images/rothbart-chernobyl-gauges-web.jpg
  caption: 'Courtesy of Michael Forster Rothbart'
include_categories:   
  - arts
  - food
  - flora
  - media
  - people
  - pop
  - science
  - time
sidebar:
  - nav: splash
permalink: /
---

{% for c in page.include_categories %}

<div id="{{ c }}" class="pane">

<h3>{{ site.data.content.display_categories[c] }}</h3>

{% assign category_projects = site.projects | where: 'categories', c  %}

{% include collection_row projects = category_projects  %}
  
</div>

{% endfor %}