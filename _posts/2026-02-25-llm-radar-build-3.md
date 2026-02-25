---
layout: post
title: "LLM Radar 만들기 3화: Perplexity가 내 사이트를 못 읽었다"
date: 2026-02-25 21:00:00 +0900
categories: [빌드인퍼블릭, LLM-Radar]
tags: [LLMO, LLM검색최적화, GoogleSearchConsole, SEO, 인덱싱]
description: "Perplexity에게 내 사이트를 분석해달라고 했더니 '크롤링 제한'이라고 했다. 그게 LLMO보다 더 근본적인 문제를 발견하게 해줬다."
---

2화 마지막에 이렇게 썼다.

> "3화: 이 5개 인사이트를 실제로 적용해본다 — 포맷, 구조, 키워드를 바꿔서 다시 스캔"

계획이 바뀌었다. 더 기초적인 문제를 발견했기 때문에.

---

## Perplexity에게 직접 물어봤다

2화 작업을 마치고, 역으로 테스트를 해봤다.

Perplexity에게 물었다.

> "jameskwon07.github.io를 읽어보고 이 블로그가 어떤 키워드를 다루는지 알려줘."

답변:

> "해보니까 저 URL도 이 환경에서는 직접 내용을 가져오지 못합니다. (GitHub Pages 일부 도메인/경로가 크롤링 제한이 걸려 있는 듯합니다.)"

처음엔 GitHub Pages 문제인 줄 알았다.

---

## 실제 이유는 달랐다

사이트 자체는 멀쩡했다. 아무 브라우저에서나 열린다.

Perplexity가 못 읽은 건 "크롤링 제한" 때문이 아니었다.

**아직 Google 검색 인덱스에 등록이 안 돼있었기 때문이다.**

Perplexity는 자체 크롤러로 실시간으로 웹을 긁는 게 아니다. 기본적으로 이미 인덱싱된 정보를 가져온다. 새 사이트, 신규 콘텐츠는 Google이 먼저 알아야 한다.

내 블로그는 만든 지 3일밖에 안 됐다. Google이 아직 모르는 사이트였다.

---

## 순서가 틀렸다

LLMO 실험을 하겠다고 18개 질문으로 스캔하고, Perplexity 답변을 분석하고, 콘텐츠 전략을 짰다.

근데 기초가 빠져있었다.

Google이 내 사이트를 모르면, LLM도 내 사이트를 모른다.

검색 엔진 인덱싱이 안 된 상태에서 LLMO를 논하는 건, 간판도 없는 가게 앞에서 마케팅을 고민하는 것과 같았다.

---

## Google Search Console 등록

오늘 바로 등록했다.

1. [Google Search Console](https://search.google.com/search-console/) 접속
2. `https://jameskwon07.github.io` 속성 추가
3. 소유권 인증 — HTML 메타태그를 `_config.yml`에 추가
4. `sitemap.xml` 제출

Jekyll을 쓰면 `jekyll-sitemap` 플러그인이 자동으로 사이트맵을 만들어준다. 이미 설정돼있었다. 제출만 하면 됐다.

등록 완료. Google이 이제 내 사이트를 안다.

---

## 사이트맵이 왜 중요한가

사이트맵은 Google에게 "이 URL들을 크롤해줘"라고 알려주는 파일이다.

없어도 Google이 발견할 수 있다. 하지만 시간이 걸린다. 몇 주, 몇 달.

사이트맵을 제출하면 Google이 우선적으로 크롤한다. 인덱싱 속도가 빨라진다.

그리고 Google이 인덱싱하면, Perplexity도 내 사이트를 읽을 수 있게 된다.

---

## LLMO 이전에 필요한 것

2화에서 Perplexity가 정리해줬던 내용이 있다.

> "사이트의 robots.txt 설정 확인, 구조화된 데이터(Schema Markup) 추가, 외부 사이트의 리뷰와 언급 늘리기"

당시엔 "콘텐츠 전략" 얘기인 줄 알았다.

근데 그 전에 더 기본적인 게 있었다.

**LLM이 내 콘텐츠에 접근할 수 있어야 한다.**

검색 엔진 인덱싱 → LLM 학습/검색 참조 → 내 콘텐츠 인용

이 순서다. 첫 번째 단계가 없으면 나머지가 의미없다.

---

## 다음 화 예고

Google Search Console 등록 후 실제로 인덱싱이 되는지 확인할 것이다.

그리고 나서 2화에서 못한 걸 한다 — 포맷과 구조를 바꿔서 다시 스캔.

기초를 갖췄으니 이제 실험을 시작할 수 있다.

---

**← 이전 화:** [2화: Perplexity에 직접 물어봤다](https://jameskwon07.github.io/2026/02/23/llm-radar-build-2/)

*[jameskwon07.github.io](https://jameskwon07.github.io) | LLM Radar 빌드 인 퍼블릭 시리즈*
