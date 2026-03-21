---
title: "搜索"
date: 2026-03-10
type: page
layout: page
draft: false
---

## 搜索

输入关键词搜索文章：

<input type="text" id="searchInput" placeholder="搜索..." 
       style="width: 100%; max-width: 400px; padding: 10px; 
              border: 1px solid #ddd; border-radius: 6px;
              font-size: 16px;">

<div id="results" style="margin-top: 2rem;">
{{ range (where .Site.Pages "Type" "post").ByDate.Reverse }}
  <div class="result-item" data-title="{{ .Title | lower }}">
    <a href="{{ .RelPermalink }}" style="font-size: 1.1rem;">{{ .Title }}</a>
    <span style="color: #888; font-size: 0.9rem; margin-left: 10px;">{{ .Date.Format "2006-01-02" }}</span>
  </div>
{{ end }}
</div>

<script>
const input = document.getElementById('searchInput');
const items = document.querySelectorAll('.result-item');

input.addEventListener('input', (e) => {
  const q = e.target.value.toLowerCase();
  items.forEach(item => {
    const title = item.dataset.title;
    item.style.display = title.includes(q) ? 'block' : 'none';
  });
});
</script>
