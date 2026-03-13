---
layout: default
title: 搜索
---

<article>
  <h1>搜索</h1>

  <div class="search-container">
    <input type="text" id="search-input" placeholder="输入关键词搜索文章..." class="search-input">
    <div id="search-results" class="search-results"></div>
  </div>
</article>

<script>
// 简单的客户端搜索功能
const searchInput = document.getElementById('search-input');
const searchResults = document.getElementById('search-results');

// 获取所有文章的数据
const posts = [
  {% for post in site.posts %}
    {
      title: "{{ post.title | escape }}",
      url: "{{ post.url | relative_url }}",
      date: "{{ post.date | date: "%Y-%m-%d" }}",
      content: "{{ post.content | strip_html | strip_newlines | escape | truncatewords: 100 }}"
    }{% unless forloop.last %},{% endunless %}
  {% endfor %}
];

searchInput.addEventListener('input', function(e) {
  const query = e.target.value.toLowerCase();

  if (query.length === 0) {
    searchResults.innerHTML = '';
    return;
  }

  const results = posts.filter(post => {
    return post.title.toLowerCase().includes(query) ||
           post.content.toLowerCase().includes(query);
  });

  if (results.length === 0) {
    searchResults.innerHTML = '<p style="color: var(--text-secondary); text-align: center; padding: 2rem;">没有找到相关文章</p>';
    return;
  }

  searchResults.innerHTML = results.map(post => `
    <div class="search-result-item">
      <a href="${post.url}" class="search-result-title">${post.title}</a>
      <time class="search-result-date">${post.date}</time>
      <p class="search-result-content">${post.content.substring(0, 150)}...</p>
    </div>
  `).join('');
});
</script>

<style>
.search-container {
  margin-top: 2rem;
}

.search-input {
  width: 100%;
  padding: 1rem 1.5rem;
  font-size: 1rem;
  border: 2px solid var(--border-color);
  border-radius: 8px;
  background: var(--card-bg);
  color: var(--text-primary);
  transition: border-color 0.2s ease;
}

.search-input:focus {
  outline: none;
  border-color: var(--accent-color);
}

.search-results {
  margin-top: 2rem;
}

.search-result-item {
  padding: 1.5rem;
  margin-bottom: 1rem;
  background: var(--card-bg);
  border-radius: 8px;
  border: 1px solid var(--border-color);
  transition: box-shadow 0.2s ease;
}

.search-result-item:hover {
  box-shadow: 0 2px 8px var(--shadow-color);
}

.search-result-title {
  display: block;
  font-size: 1.2rem;
  font-weight: 500;
  color: var(--accent-color);
  text-decoration: none;
  margin-bottom: 0.5rem;
}

.search-result-title:hover {
  text-decoration: underline;
}

.search-result-date {
  display: block;
  font-size: 0.85rem;
  color: var(--text-secondary);
  margin-bottom: 0.75rem;
}

.search-result-content {
  font-size: 0.95rem;
  line-height: 1.6;
  color: var(--text-secondary);
}
</style>
