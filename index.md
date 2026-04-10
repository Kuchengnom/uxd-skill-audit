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

        {% comment %} Vorschaubild: skill_github hat Vorrang, dann skill_reviewed parsen, dann skill_image {% endcomment %}
        {% assign _gh_ref = post.skill_github | default: post.skill_reviewed %}
        {% if _gh_ref contains "/" %}
          {% assign skill_parts = _gh_ref | split: "/" %}
          {% assign skill_owner = skill_parts[0] %}
          {% assign skill_repo  = skill_parts[1] %}
          <div class="post-list-item__thumb">
            <img
              src="https://opengraph.githubassets.com/1/{{ skill_owner }}/{{ skill_repo }}"
              alt="{{ _gh_ref }} GitHub-Vorschau"
              loading="lazy"
              onerror="this.parentElement.classList.add('post-list-item__thumb--fallback'); this.src='https://github.com/{{ skill_owner }}.png?size=96';"
            >
          </div>
        {% elsif post.skill_image %}
          <div class="post-list-item__thumb">
            <img src="{{ post.skill_image }}" alt="{{ post.title }}" loading="lazy">
          </div>
        {% else %}
          <div class="post-list-item__thumb post-list-item__thumb--placeholder"></div>
        {% endif %}

        <div class="post-list-item__body">
          <div class="post-list-item__meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">{% include date-de.html date=post.date %}</time>
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
        </div>

      </li>
      {% endfor %}
    </ul>

  </div>
</div>
