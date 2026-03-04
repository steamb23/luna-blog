---
layout: default
title: 글
permalink: /blog/
---

<div class="container blog-list">
  <h1 class="section-title">글 목록</h1>
  <div class="post-grid">
    {% for post in site.posts %}
    <article class="post-card">
      <div class="post-card-inner">
        <time class="post-date" datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%Y. %m. %d" }}
        </time>
        <h3 class="post-card-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
        {% if post.excerpt %}
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 80 }}</p>
        {% endif %}
        {% if post.tags.size > 0 %}
        <div class="post-tags">
          {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</div>
