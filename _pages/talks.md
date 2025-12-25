---
permalink: /talks/
title: "Presentations & Talks"
author_profile: true
layout: single
---

<ul class="talk-list">
  {% assign talks = site.talks | sort: 'date' | reverse %}
  {% for talk in talks %}
  <li>
    <strong>{{ talk.title }}</strong> <em>({{ talk.type }})</em><br>
    {{ talk.event }}, {{ talk.location }} ({{ talk.date | date: "%B %Y" }})<br>
    {% if talk.slides %}[Slides]({{ talk.slides }}){% endif %}
    {% if talk.video %} | [Video]({{ talk.video }}){% endif %}
  </li>
  {% endfor %}
</ul>
