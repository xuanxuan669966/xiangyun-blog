---
layout: default
---

<div class="posts-grid">
  {% for post in site.posts %}
    <article class="post-card">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>

      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
        {% if post.categories %}
          <span class="post-category">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="vertical-align: -2px; margin-right: 2px;">
              <path d="M20.59 13.41l-7.17 7.17a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82z"></path>
              <line x1="7" y1="7" x2="7.01" y2="7"></line>
            </svg>
            {{ post.categories | first }}
          </span>
        {% endif %}
      </div>

      <p class="post-excerpt">{{ post.excerpt }}</p>

      <div class="post-footer">
        <a href="{{ post.url }}" class="read-more">
          阅读全文
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="5" y1="12" x2="19" y2="12"></line>
            <polyline points="12 5 19 12 12 19"></polyline>
          </svg>
        </a>
      </div>
    </article>
  {% endfor %}
</div>

<div style="text-align: center; margin-top: 3rem;">
  <a href="/categories" class="btn">查看所有文章</a>
</div>
