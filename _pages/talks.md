---
permalink: /talks/
title: "Presentations & Talks"
author_profile: true
layout: collection
---
<style>

/* .talks-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, 320px);
  gap: 1.5rem;
  justify-content: center;
  width: 100%;
} */

.talks-grid {
  width: 100%;
  max-width: 1200px;
  margin: 2rem auto; 
}


/* .talks-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-top: 1rem;
} */

.talk-card {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.05);
  overflow: hidden;
  /* width: 320px;        /* optional but safe */
  /* height: 360px; */
  /* display: flex; */
  /* flex-direction: column; */ */
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}
/* .talk-card {
  width: 320px;     
  height: 360px;
  display: flex;
  flex-direction: column;
} */
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
  color: #667eea;
  text-decoration: none;
  font-weight: 500;
}

.talk-links a:hover {
  text-decoration: underline;
}
.talk-card-link {
  text-decoration: none;
  color: inherit;
  display: block;
  width: auto;
}
.talk-card-link:hover .talk-title {
  color: #667eea;
}
</style>

<div class="talks-grid">
  {% assign talks = site.talks | sort: 'date' | reverse %}
  {% for talk in talks %}
  <a href="{{ talk.url }}" class="talk-card-link">
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
  </a>
  {% endfor %}
</div>