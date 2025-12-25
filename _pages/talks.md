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

.talk-list {
  list-style: none;
  padding-left: 0;
}
.talk-list li {
  margin-bottom: 1.2em;
  border-bottom: 1px solid #e0e0e0;
  padding-bottom: 0.8em;
}
.talk-list strong {
  font-size: 1.1em;
}
.talk-list em {
  color: #555;
}
