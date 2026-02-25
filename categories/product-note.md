---
layout: default
title: "제품 노트"
permalink: /categories/product-note/
---

# 📝 제품 노트

솔로프레너가 만든 제품을 직접 써보고 솔직하게 피드백합니다.  
주관적인 사용 경험과 객관적인 데이터를 함께 씁니다.

---

<ul>
  {% assign posts = site.posts | where_exp: "post", "post.categories contains '제품노트'" %}
  {% for post in posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
    <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
  </li>
  {% endfor %}
</ul>

---

[← 홈으로](/)
