---
layout: single
title: "The Reactor Room: <br/> An Immersive Chornobyl Exhibition"
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
  *The Reactor Room* is a digital installation that seeks to facilitate public engagement with the Chornobyl catastrophe and its history and mythology. It features work from students in Professor José Vergara’s course RUSSB220 Chornobyl taught at Bryn Mawr College (Fall 2023) and RUSS043 Chernobyl: Nuclear Narratives and the Environment at Swarthmore College (Spring 2020), as well as projects developed by the Bryn Mawr Digital Scholarship Summer Fellows (Summer 2023). To begin, see [nuclear energy basics](./projects/nuclear-power/). 
</div>

{% for c in page.include_categories %}

<div id="{{ c }}" class="pane">

<h3>{{ site.data.content.display_categories[c] }}</h3>

{% assign category_projects = site.projects | where: 'categories', c  %}

{% include collection_row projects = category_projects  %}
  
</div>

{% endfor %}
