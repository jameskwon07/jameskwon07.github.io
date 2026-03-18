---
layout: default
title: "메이커노트"
permalink: /categories/maker-note/
---

# 🔧 메이커노트

직접 만드는 제품에 대한 기획, 설계, 의사결정 기록.

---

<ul>
  {% for post in site.categories['메이커노트'] %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
    <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
  </li>
  {% endfor %}
</ul>

---

[← 홈으로](/)
