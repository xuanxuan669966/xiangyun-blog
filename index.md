---
layout: default
---

## 最新文章

{% for post in site.posts limit:5 %}
  <div style="margin-bottom: 2rem;">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <div class="meta">
      <time>{{ post.date | date: "%Y-%m-%d" }}</time>
      {% if post.categories %}
        <span> · {{ post.categories | join: ", " }}</span>
      {% endif %}
    </div>
    <p>{{ post.excerpt }}</p>
  </div>
{% endfor %}

<a href="/categories" style="display: inline-block; margin-top: 2rem; padding: 0.5rem 1rem; border: 1px solid #000;">查看所有文章</a>
