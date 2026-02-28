---
layout: post
title: "LLM Radar 만들기 4화: 경쟁사를 직접 뜯어봤다 — Gauge 시리즈 1"
date: 2026-02-28 12:00:00 +0900
categories: [빌드인퍼블릭, LLM-Radar]
tags: [LLMO, LLM검색최적화, 경쟁사분석, GEO, AEO, SaaS]
description: "Gauge, Otterly, Profound. AI 검색 가시성 시장의 경쟁사들을 직접 뜯어봤다. 그리고 내가 어디에 서 있어야 하는지 생각했다."
---

3화 마지막에 이렇게 썼다.

> "site:jameskwon07.github.io 검색 결과가 뜨는 날, 재스캔을 돌린다."

아직 안 떴다. 기다리는 중이다.

그래서 기다리는 동안 다른 걸 했다. 경쟁사를 직접 뜯어봤다.

---

## 발단은 Product Hunt이었다

우연히 Product Hunt에서 흥미로운 글을 발견했다.

> *"Case Study: How Product Hunt Can Improve AI Visibility in 2026"*

Product Hunt이 직접 쓴 케이스 스터디였다. 요약하면 이렇다.

> "ChatGPT 같은 AI가 제품 추천할 때 Product Hunt을 거의 인용하지 않았다. 왜 그런지 분석했고, 바꿀 수 있었다. AI 인용률이 0%에서 지속적으로 인용되는 수준으로 올라갔다."

그리고 그 글에서 **Gauge**라는 툴이 언급됐다. AI 가시성을 측정하는 데 사용한 도구라고.

---

## Gauge를 찾아봤다

`withgauge.com`

**"AI Visibility Platform & Analytics for Generative Engine Optimization"**

홈페이지에 들어가자마자 느낀 것: LLM Radar와 하는 일이 같다.

하지만 대상이 달랐다. 마케팅 팀, 에이전시, 기업 담당자. 대규모 조직을 위한 툴이었다.

블로그에는 "2900만 AI 답변을 분석했다", "수백만 AI 답변을 추적하며 배운 것들" 같은 글이 있다. 데이터가 많다. 신뢰가 간다.

근데 혼자서 제품을 만들고 운영하는 사람이 이 툴을 쓰기엔 진입장벽이 높다.

---

## Otterly.ai, Profound도 봤다

**Otterly.ai**도 비슷했다. 기능도, 구조도, 타겟도.

**Profound**은 더 명확하게 엔터프라이즈 대상이었다.

---

## 공통점이 보였다

세 서비스를 다 보고 나서 공통점을 발견했다.

**모두 영어다.** 한국어 서비스가 없다.

**모두 셀프서비스다.** "툴 드릴게요, 알아서 쓰세요."

**대상이 조직이다.** 마케팅 팀, 에이전시, 중견기업 이상.

그러면 나는 어디 있어야 할까.

---

## 나는 어디에 서 있어야 하는가

솔직히 처음엔 흔들렸다.

Gauge가 이미 잘 하고 있는데, 내가 뭘 할 수 있을까.

근데 생각해보면 내가 만들려는 건 처음부터 Gauge가 아니었다.

**한국어로**, 데이터를 던져주고 끝내는 게 아니라 **함께 읽고, 함께 다음 스텝을 고민하는 것**.

이건 Gauge가 할 수 없는 영역이다. 할 생각도 없을 것이다. 한 명 한 명과 함께하는 건 대규모 SaaS의 비즈니스 모델이 아니다.

---

## 경쟁사가 알려준 것

경쟁사 분석을 하면서 하나를 배웠다.

Gauge의 블로그에 이런 말이 있었다.

> "모델 업데이트마다 AI 인용 패턴이 바뀐다. 지속적인 모니터링이 필수다."

이게 LLM Radar가 일회성 서비스가 아니어야 하는 이유다.

AI 검색은 고정된 게 아니다. ChatGPT가 업데이트되면 어제까지 잘 나오던 제품이 오늘 안 나올 수 있다. 반대로 노출이 없었던 제품이 갑자기 추천될 수도 있다.

한 번 측정하고 끝이 아니다. 계속 봐야 한다.

---

## 지금 상황 정리

인덱싱은 아직 안 됐다. Perplexity 재스캔도 못 했다.

근데 이번 화에서 더 중요한 걸 정리한 것 같다.

- 시장이 있다 — Gauge, Otterly, Profound이 이미 존재한다는 건 수요가 증명됐다는 뜻이다
- 공백이 있다 — 한국어, 셀프서비스가 아닌 것, 조직이 아닌 개인
- 내가 할 수 있는 것이 있다 — 데이터 + 해석 + 함께하는 것, 한국어로

기다리는 동안 생각이 정리됐다.

---

## 다음 화 예고

Gauge 시리즈 2 — LLM Radar로 Gauge를 직접 조사한다.

AI는 Gauge를 어떻게 설명하는가. 어떤 질문에서 언급되고, 어떤 질문에서 빠지는가. 경쟁사를 측정 대상으로 삼아서 LLM Radar가 실제로 어떤 정보를 뽑아내는지 공개한다.

---

**← 이전 화:** [3화: Perplexity가 내 사이트를 못 읽었다](https://jameskwon07.github.io/2026/02/25/llm-radar-build-3/) | **→ 다음 화:** [5화: Gauge를 AI로 검색해봤다 — Gauge 시리즈 2](https://jameskwon07.github.io/2026/03/01/llm-radar-build-5/)

비슷한 고민 있으시면 편하게 연락주세요. → [contact@voidops.space](mailto:contact@voidops.space)

*[jameskwon07.github.io](https://jameskwon07.github.io) | LLM Radar 빌드 인 퍼블릭 시리즈*
