---
title: "Blog"
permalink: /blog/
layout: default
---

<ul>
  {% raw %}{% for post in site.posts %}{% endraw %}
    <li>
      <a href="{% raw %}{{ post.url | relative_url }}{% endraw %}">
        {% raw %}{{ post.title }}{% endraw %}
      </a> — {% raw %}{{ post.date | date: "%Y-%m-%d" }}{% endraw %}
    </li>
  {% raw %}{% endfor %}{% endraw %}
</ul>
