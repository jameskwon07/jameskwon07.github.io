---
layout: default
title: "LLM Radar 빌드 로그"
permalink: /categories/llm-radar/
---

# 🛰 LLM Radar 빌드 로그

AI 검색 최적화 도구를 직접 만들면서 기록하는 시리즈.  
ChatGPT, Perplexity가 내 콘텐츠를 알고 있는지 측정합니다.

---

<ul>
  {% for post in site.categories['LLM-Radar'] %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
    <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
  </li>
  {% endfor %}
</ul>

---

[← 홈으로](/)
