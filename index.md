---
layout: default
title: UX Skills Review
---

<div class="page-section">
  <div class="container">
    <p style="max-width: 55ch; font-size: 1.125rem; color: var(--color-text-muted); margin-bottom: var(--space-2xl);">
      Design-Methodik trifft auf Claude-Skills. Jeder Post erklaert eine Technik, evaluiert einen existierenden Skill danach — und macht die Bewertungskriterien transparent.
    </p>

    <div class="section-title">Neueste Beitraege</div>
    <ul class="post-list">
      {% for post in site.posts %}
      <li class="post-list-item">
        <div class="post-list-item__meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d. %B %Y" }}</time>
          {% if post.category %}
          <span class="tag">{{ post.category }}</span>
          {% endif %}
          {% if post.verdict %}
          <span class="verdict verdict--{{ post.verdict | downcase }}" style="padding: 0.15em 0.5em; font-size: 0.75rem; margin: 0;">
            {% case post.verdict %}
              {% when 'solide' %}Solide
              {% when 'vertrauen' %}Vertrauen mit Vorbehalt
              {% when 'vorsicht' %}Vorsicht
              {% when 'ablehnen' %}Nicht empfohlen
              {% else %}{{ post.verdict }}
            {% endcase %}
          </span>
          {% endif %}
        </div>
        <div class="post-list-item__title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </div>
        {% if post.excerpt %}
        <div class="post-list-item__excerpt">{{ post.excerpt | strip_html | truncate: 180 }}</div>
        {% endif %}
      </li>
      {% endfor %}
    </ul>

  </div>
</div>
