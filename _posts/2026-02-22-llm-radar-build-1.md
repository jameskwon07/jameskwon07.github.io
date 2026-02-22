---
layout: post
title: "LLM Radar 만들기 1화: 내 블로그가 AI 검색에 뜨는지 확인하고 싶었다"
date: 2026-02-22 09:00:00 +0900
categories: [빌드인퍼블릭, LLM-Radar]
tags: [LLMO, LLM검색최적화, FastAPI, MSA, Perplexity, Claude]
description: "ChatGPT, Perplexity에 내 블로그가 언급되는지 추적하는 도구 LLM Radar를 만들기 시작했다. 경쟁사는 월 $500, 한국어 서비스는 없다."
---


> 빌드 인 퍼블릭 시리즈 | 2026년 2월 22일

---

## 시작은 단순한 궁금증이었다

요즘 ChatGPT에 "블로그 개발 공부 어디서 해?"라고 물어보는 사람이 SEO 검색보다 많다는 걸 체감한다.

그런데 내 블로그 codingbridge.blog가 이런 AI 답변에 뜨고 있을까?

확인할 방법이 없었다. Google Analytics는 구글 검색을 보여주지만 ChatGPT, Claude, Perplexity의 답변에 내 콘텐츠가 언급되는지는 아무데서도 안 보여준다.

그래서 직접 만들기로 했다.

---

## 이미 있는 서비스들은 비싸다

찾아보니 이런 걸 해주는 서비스가 이미 있다:

- **Profound** — 월 $500. 기업용이다.
- **Otterly.ai** — 영어 전용. 한국 브랜드 추적에는 아쉽다.
- **Goodie AI** — 기능은 좋은데 역시 비싸다.

한국어 경쟁사는 없다. 그리고 나는 이걸 직접 만들 수 있다.

---

## 핵심 아이디어: 3단계 파이프라인

LLM이 나를 언급하는지 확인하려면:

1. **키워드 등록** — "AI 카피라이팅", "개발 블로그" 같은 내가 노출되고 싶은 주제
2. **질문 자동 생성** — Claude API를 써서 "AI 카피라이터 추천해줘", "개발 블로그 어디서 봐?" 같은 질문을 자동으로 만들어냄
3. **LLM에 실제 질문** — Perplexity API로 진짜 AI 검색처럼 질문하고, 답변에 내 브랜드/도메인이 언급되는지 확인

노출률 = (언급된 질문 수 / 전체 질문 수) × 100

---

## 아키텍처: MSA로 만든 이유

처음엔 하나의 Python 스크립트로 만들까 했다. 근데 블로그에 쓰려면 좀 더 "진짜 같은" 프로젝트여야겠다 싶었다.

MSA(Microservices Architecture)로 만들었다:

```
[Streamlit Frontend :8503]
          │
    [API Gateway :8000]
    ┌─────┼──────┬──────┐
    │     │      │      │
[keyword] [query] [checker] [result]
  :8001    :8002   :8003     :8004
```

각 서비스는 FastAPI로 만들었고, 역할이 명확히 분리되어 있다:

- **keyword-service**: SQLite에 브랜드/키워드 저장
- **query-service**: Claude API로 테스트 질문 생성
- **checker-service**: Perplexity API로 실제 LLM 체크
- **result-service**: 스캔 결과 저장 + 통계
- **gateway**: 모든 서비스를 프록시로 연결

---

## 개발 환경 vs 프로덕션

API 키 없이도 개발할 수 있게 Mock 모드를 만들었다.

`ENV=dev`면:
- 질문 생성 → 미리 만들어둔 템플릿에서 랜덤 선택
- LLM 체크 → 20% 확률로 "언급됨" 시뮬레이션

`ENV=prod`면:
- 질문 생성 → 실제 Claude API 호출
- LLM 체크 → Perplexity API (없으면 Claude 폴백)

이 덕분에 API 비용 없이 UI를 먼저 다 만들고 나중에 진짜 API 연결만 했다.

---

## 현재 상태

v0.1이 완성됐다:

- ✅ 브랜드/키워드 등록 UI
- ✅ 스캔 실행 (질문 생성 → LLM 체크 → 결과 저장)
- ✅ 노출률 수치 + 언급된/안 된 질문 시각화
- ✅ 트렌드 차트 (시간별 노출률 변화)
- ✅ Docker Compose로 원클릭 실행
- ✅ 로컬 개발용 start.sh

실제로 내 블로그 `codingbridge.blog`를 등록하고 "개발 블로그", "AI 카피라이팅" 키워드로 첫 스캔을 돌렸더니:

**노출률 0%.**

예상했다. 아직 블로그 글이 많지 않고, 내가 작성한 콘텐츠가 LLM 학습 데이터에 충분히 포함되어 있지 않다. 이걸 올리면서 추적해볼 생각이다.

---

## 다음 화 예고

- 2화: Perplexity API 연동 삽질기 (rate limit, timeout 처리)
- 3화: 노출률 0%에서 올리기 위한 콘텐츠 전략 실험
- 4화: 스케줄러 추가 — 매일 자동 스캔 + 텔레그램 알림

---

## 코드 / 사용해보기

현재 로컬 실행만 지원한다. Docker Compose가 있으면:

```bash
git clone [repo]
cp .env.example .env
# .env에 ANTHROPIC_API_KEY, PERPLEXITY_API_KEY 입력
docker-compose up -d
# http://localhost:8503 접속
```

API 키 없이 Mock 모드로 UI만 테스트해보고 싶다면:

```bash
bash start-dev.sh
```

---

*codingbridge.blog에서 개발하면서 배운 것들을 씁니다. 이 시리즈는 실제로 만들면서 쓰는 빌드 인 퍼블릭 기록입니다.*
