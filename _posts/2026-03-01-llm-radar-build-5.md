---
layout: post
title: "LLM Radar 만들기 5화: Gauge를 AI로 검색해봤다 — Gauge 시리즈 2"
date: 2026-03-01 06:00:00 +0900
categories: [빌드인퍼블릭, LLM-Radar]
tags: [LLMO, LLM검색최적화, 경쟁사분석, GEO, Gauge, AI가시성]
description: "AI 검색 가시성을 측정해주는 Gauge를, LLM Radar로 직접 측정해봤다. 결과는 예상 밖이었다."
---

4화에서 Gauge를 발견하고 이렇게 썼다.

> "AI 가시성을 높여주는 서비스가 정작 자기 자신의 AI 가시성이 얼마나 될까."

직접 측정해봤다.

---

## 측정 방법

LLM Radar로 `withgauge.com`을 브랜드로 등록하고, 경쟁사 분석용 질문 7개로 Perplexity에 실제 질문을 던졌다.

질문은 이렇다:

1. How can I check if my brand is mentioned in ChatGPT?
2. What tools can track my brand visibility in LLM search results?
3. Recommend an AI search monitoring service
4. How do marketers measure AI search performance?
5. Recommend GEO optimization tools
6. Compare AI search optimization SaaS tools
7. What services track brand visibility on ChatGPT and Perplexity?

Gauge가 하는 일을 정확하게 묻는 질문들이다. 만약 Gauge의 AI 가시성이 높다면, 이 질문들에서 언급이 나와야 한다.

---

## 결과: 노출률 0%

7개 질문, 0번 언급.

Gauge는 단 한 번도 Perplexity 답변에 등장하지 않았다.

대신 이런 이름들이 나왔다.

- **Q2 (LLM 추적 도구)**: Nightwatch, Profound, Semrush
- **Q3 (AI 모니터링 서비스 추천)**: Promptwatch, Profound
- **Q5 (GEO 최적화 도구)**: Semrush, Moz, Ahrefs 계열
- **Q6 (AI 검색 최적화 SaaS 비교)**: Otterly, AIclicks, Siftly
- **Q7 (ChatGPT·Perplexity 브랜드 추적)**: Siftly, Frase, OtterlyAI

Gauge의 이름은 없었다.

---

## 뭘 의미하는가

두 가지 해석이 가능하다.

**첫째, Gauge는 아직 신생 서비스다.**

Perplexity가 참조하는 데이터는 웹에 이미 충분히 쌓인 정보다. Gauge가 최근에 생겼거나, 외부 언급이 아직 많지 않다면 AI 답변에 포함되기 어렵다.

**둘째, AI 가시성 툴이라고 해서 자기 자신의 AI 가시성이 높은 건 아니다.**

이게 더 흥미로운 지점이다. Gauge는 "AI 검색에서 당신의 브랜드가 보이도록 도와드립니다"라고 말한다. 그런데 "AI search monitoring service 추천해줘"라는 질문에 정작 Gauge 자신은 등장하지 않는다.

측정 도구를 만들었다고 해서, 그 측정 도구 자신이 측정 대상이 되는 건 아니다.

---

## 그게 왜 중요한가

Gauge의 블로그에서 이런 말을 읽었다.

> "모델 업데이트마다 AI 인용 패턴이 바뀐다. 지속적인 모니터링이 필수다."

맞는 말이다. 그리고 이 데이터가 그것을 증명한다.

아무리 좋은 툴을 만들어도, AI 검색에서 보이지 않으면 잠재 고객은 그 툴의 존재조차 모른다. 콘텐츠가 없으면, 인용이 없다. 인용이 없으면, AI 검색에서 보이지 않는다.

이 악순환을 끊는 방법은 하나다. 콘텐츠를 쌓고, 외부 언급을 만들고, 시간이 지나는 것.

---

## LLM Radar는 어떨까

같은 질문 7개를 `jameskwon07.github.io`로도 돌려볼 예정이다.

아마 결과는 비슷할 것이다. 아직 인덱싱도 완료되지 않았고, 외부 언급도 없다.

중요한 건 지금의 0%가 아니라, 다음 스캔에서 달라지는지다. 그 변화를 여기서 계속 공개한다.

---

**← 이전 화:** [4화: 경쟁사를 직접 뜯어봤다 — Gauge 시리즈 1](https://jameskwon07.github.io/2026/02/28/llm-radar-build-4/)

비슷한 고민 있으시면 편하게 연락주세요. → [contact@voidops.space](mailto:contact@voidops.space)

*[jameskwon07.github.io](https://jameskwon07.github.io) | LLM Radar 빌드 인 퍼블릭 시리즈*
