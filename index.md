---
layout: default
title: Home
---

# Coding Bridge 🌉

솔로프레너의 관점으로 제품을 만들고, 쓰고, 기록합니다.

---

## 🛰 [LLM Radar 빌드 로그](/categories/llm-radar/)

AI 검색 최적화 도구를 직접 만드는 여정.

<ul>
  {% assign llm_posts = site.posts | where_exp: "post", "post.categories contains 'LLM-Radar'" %}
  {% for post in llm_posts limit: 3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
  </li>
  {% endfor %}
</ul>

[전체 보기 →](/categories/llm-radar/)

---

## 📝 [제품 노트](/categories/product-note/)

솔로프레너가 만든 제품을 직접 써보고 피드백합니다.

<ul>
  {% assign pn_posts = site.posts | where_exp: "post", "post.categories contains '제품노트'" %}
  {% for post in pn_posts limit: 3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
  </li>
  {% endfor %}
</ul>

[전체 보기 →](/categories/product-note/)

---

*by James Kwon · [GitHub](https://github.com/jameskwon07)*
