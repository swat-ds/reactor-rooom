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
  - history
  - media
  - people
  - pop
  - religion
  - science
  - time
sidebar:
  - nav: splash
permalink: /home/
---


<div id="mission" markdown="1">
  *The Reactor Room* is a digital installation that seeks to facilitate public engagement with the Chornobyl catastrophe and its history and mythology. It features work from students in Professor José Vergara’s course RUSSB220 Chornobyl taught at Bryn Mawr College (Fall 2023) and RUSS043 Chernobyl: Nuclear Narratives and the Environment at Swarthmore College (Spring 2020), as well as projects developed by the Bryn Mawr Digital Scholarship Summer Fellows (Summer 2023). To begin, see [nuclear energy basics](./projects/nuclear-power/). 
</div>

{% for c in page.include_categories %}

<div id="{{ c }}" class="pane">

  <h3>{{ site.data.content.display_categories[c] }}</h3>

  {% assign category_projects = site.projects | where: 'categories', c %}

  {% for course in site.data.content.courses %}
    {% if forloop.first %}
      {% assign sorted_projects = category_projects | where: 'course', course %}
    {% else %}
      {% assign course_projects = category_projects | where: 'course', course %}
      {% for p in course_projects %}
        {% assign sorted_projects = sorted_projects | push: p %}
      {% endfor %}
    {% endif %}
  {% endfor %}
  
  {% include collection_row projects = sorted_projects  %}

</div>

{% endfor %}
