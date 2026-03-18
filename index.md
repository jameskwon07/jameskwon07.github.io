---
layout: default
title: Home
---

# Coding Bridge 🌉

제 눈으로 보고, AI에게 물어봅니다.

---

## 🛰 [LLM Radar 빌드 로그](/categories/llm-radar/)

AI 검색 최적화 도구를 직접 만드는 여정.

<ul>
  {% for post in site.categories['LLM-Radar'] limit: 3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
  </li>
  {% endfor %}
</ul>

[전체 보기 →](/categories/llm-radar/)

---

## 🔧 [메이커노트](/categories/maker-note/)

직접 만드는 제품에 대한 기획, 설계, 의사결정 기록.

<ul>
  {% for post in site.categories['메이커노트'] limit: 3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
  </li>
  {% endfor %}
</ul>

[전체 보기 →](/categories/maker-note/)

---

## 📝 [제품 노트](/categories/product-note/)

솔로프레너가 만든 제품을 직접 써보고 피드백합니다.

<ul>
  {% for post in site.categories['제품노트'] limit: 3 %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
  </li>
  {% endfor %}
</ul>

[전체 보기 →](/categories/product-note/)

---

*by James Kwon · [GitHub](https://github.com/jameskwon07)*
