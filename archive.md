---
layout: default
title: 归档
---

<article>
  <h1>文章归档</h1>

  <div class="archive-list">
    {% for post in site.posts %}
      <div class="archive-item">
        <time>{{ post.date | date: "%Y-%m-%d" }}</time>
        <a href="{{ post.url }}">{{ post.title }}</a>
      </div>
    {% endfor %}
  </div>
</article>

<style>
.archive-list {
  margin-top: 2rem;
}

.archive-item {
  display: flex;
  gap: 1rem;
  padding: 1rem 0;
  border-bottom: 1px solid var(--border-color);
}

.archive-item:last-child {
  border-bottom: none;
}

.archive-item time {
  color: var(--text-secondary);
  font-size: 0.9rem;
  min-width: 100px;
}

.archive-item a {
  color: var(--accent-color);
  text-decoration: none;
  flex: 1;
}

.archive-item a:hover {
  text-decoration: underline;
}
</style>
