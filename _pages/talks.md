---
permalink: /talks/
title: "Presentations & Talks"
author_profile: true
layout: single
---
<style>
.talks-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-top: 1rem;
}

.talk-card {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.05);
  overflow: hidden;
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.talk-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 16px rgba(0,0,0,0.08);
}

.talk-thumbnail {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.talk-content {
  padding: 1rem 1.2rem;
}

.talk-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 0.3rem;
}

.talk-meta {
  color: #64748b;
  font-size: 0.9rem;
  margin-bottom: 0.6rem;
}

.talk-desc {
  font-size: 0.9rem;
  color: #334155;
}

.talk-links a {
  color: #2563eb;
  text-decoration: none;
  font-weight: 500;
}

.talk-links a:hover {
  text-decoration: underline;
}
</style>


<div class="talks-grid">
  {% assign talks = site.talks | sort: 'date' | reverse %}
  {% for talk in talks %}
  <div class="talk-card">
    {% if talk.thumbnail %}
      <img src="{{ talk.thumbnail }}" alt="{{ talk.title }}" class="talk-thumbnail">
    {% endif %}
    <div class="talk-content">
      <h3 class="talk-title">{{ talk.title }}</h3>
      <p class="talk-meta"><em>{{ talk.type }}</em> — {{ talk.event }}, {{ talk.location }} ({{ talk.date | date: "%B %Y" }})</p>
      <p class="talk-desc">{{ talk.content | strip_html | truncatewords: 40 }}</p>
      <p class="talk-links">
        {% if talk.slides %}<a href="{{ talk.slides }}">Slides</a>{% endif %}
        {% if talk.video %}{% if talk.slides %} | {% endif %}<a href="{{ talk.video }}">Video</a>{% endif %}
      </p>
    </div>
  </div>
  {% endfor %}
</div>
