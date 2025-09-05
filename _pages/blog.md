---
title: "Blog"
permalink: /blog/
layout: default
---

<h1>Blog</h1>

<style>
.post-card{display:flex;gap:16px;margin:18px 0;align-items:flex-start}
.post-card img{width:140px;height:90px;object-fit:cover;border-radius:6px;border:1px solid #eee}
.post-title{margin:0}
.post-meta{font-size:.9rem;color:#666;margin-top:4px}
@media (max-width:640px){.post-card{flex-direction:column}.post-card img{width:100%;height:auto}}
</style>

{% for post in site.posts %}
  {% assign thumb = post.coverImage | default: post.cover | default: post.image | default: post.featured_image %}
  <div class="post-card">
    {% if thumb %}
      <a href="{{ post.url | relative_url }}"><img src="{{ thumb | relative_url }}" alt=""></a>
    {% endif %}
    <div>
      <h3 class="post-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</div>
      {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncate: 160 }}</p>{% endif %}
    </div>
  </div>
{% endfor %}
