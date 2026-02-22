---
layout: default
title: Home
---

# Coding Bridge 🌉

**LLM 검색 최적화(LLMO)를 직접 실험하는 블로그**

ChatGPT, Claude, Perplexity가 내 콘텐츠를 알고 있을까? 직접 만든 [LLM Radar](https://github.com/jameskwon07)로 측정하면서 공유합니다.

---

## 최근 글

<ul>
  {% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%Y.%m.%d" }}</small>
    <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
  </li>
  {% endfor %}
</ul>

---

*by James Kwon · [GitHub](https://github.com/jameskwon07)*
