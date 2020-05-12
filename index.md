---
layout: single
author_profile: false
classes: ['splash']
header:
  overlay_filter: "rgba(50,50,50,.5)"
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


<div id="mission" markdown="1">
  *The Reactor Room: An Immersive Chernobyl Exhibition* is a digital installation featuring the work of students in Professor José Vergara’s course Chernobyl: Nuclear Narratives and the Environment (Spring 2020) at Swarthmore College. This interactive exhibition seeks to facilitate public engagement with the Chernobyl catastrophe and its associated mythology.
</div>

{% for c in page.include_categories %}

<div id="{{ c }}" class="pane">

<h3>{{ site.data.content.display_categories[c] }}</h3>

{% assign category_projects = site.projects | where: 'categories', c  %}

{% include collection_row projects = category_projects  %}
  
</div>

{% endfor %}