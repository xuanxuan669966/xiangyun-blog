---
layout: default
---

<h2 class="section-title">最新文章</h2>

<div class="posts-grid">
  {% for post in site.posts limit:10 %}
    <article class="post-card">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <div class="post-meta">
        <time>{{ post.date | date: "%Y-%m-%d" }}</time>
        {% if post.categories %}
          <span class="post-category">· {{ post.categories | first }}</span>
        {% endif %}
      </div>
      <p class="post-excerpt">{{ post.excerpt }}</p>
      <div class="post-footer">
        <a href="{{ post.url }}" class="read-more">
          阅读全文
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M5 12h14M12 5l7 7-7 7"/>
          </svg>
        </a>
      </div>
    </article>
  {% endfor %}
</div>

<div style="text-align: center;">
  <a href="/categories" class="btn">查看所有文章</a>
</div>
