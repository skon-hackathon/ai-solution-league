# ✈️ Find Your Partners

> **출장 목적을 이해하고, 필요한 행동을 스스로 판단·실행하며, 출장 성공에 필요한 정보와 전략까지 준비하는 AI Business Trip Agent**

---

## 1. Project Overview

**Find Your Partners**는 단순히 출장 예약을 자동화하는 서비스가 아닙니다.

사용자가 **출장 기간, 장소, 목적**을 자연어로 입력하면 AI Agent가 출장 상황을 이해하고 다음과 같은 업무를 스스로 판단합니다.

- 어떤 교통수단이 필요한가?
- 숙박이 필요한가?
- 출장 시스템 등록이 필요한가?
- 어떤 일정이 캘린더에 등록되어야 하는가?
- 출장 목적을 달성하려면 어떤 사전 조사가 필요한가?
- 어떤 출장 준비자료를 만들어야 하는가?

이후 AI Agent가 필요한 Tool/API를 선택하여 실제 업무를 실행하고,  
출장 목적에 맞는 **맞춤형 Business Briefing**까지 자동 생성합니다.

### 핵심 목표

> **출장을 편하게 만드는 AI가 아니라, 출장을 성공적으로 만드는 AI**

---

## 2. Problem

기업의 국내·해외 출장은 단순한 이동 업무가 아닙니다.

출장자는 출장 전 여러 시스템과 정보를 직접 확인하며 많은 판단을 해야 합니다.

### 기존 출장 준비 과정

```text
출장 일정 확인
    ↓
출장 시스템 등록
    ↓
교통수단 판단
    ↓
항공 / 기차 / 렌터카 예약
    ↓
호텔 필요 여부 판단 및 예약
    ↓
캘린더 일정 등록
    ↓
고객 / 행사 / 기업 정보 조사
    ↓
출장 목적에 필요한 자료 작성
    ↓
미팅 Agenda / 예상 질문 준비
    ↓
출장 수행
```

문제는 이러한 업무가 하나의 시스템에서 처리되지 않는다는 것입니다.

또한 상당수 업무는 단순 반복 작업이 아니라 **사람의 판단이 필요한 업무**입니다.

예를 들어:

- 가까운 국내 출장 → 기차 또는 차량
- 장거리 국내 출장 → 기차와 항공 비교
- 해외 출장 → 항공 + 현지 교통 + 호텔
- 당일 출장 → 숙박 불필요
- 박람회 출장 → 참가기업 및 Partnership Opportunity 분석 필요
- 고객 미팅 → 고객 최근 동향 및 관심사 분석 필요

Find Your Partners는 이러한 **판단 + 실행 + 조사 + 자료 작성**을 하나의 Agent Workflow로 통합합니다.

---

# 3. Core Concept

## Understand → Plan → Act → Prepare → Support

```text
┌──────────────────────────────┐
│         User Request         │
│ 출장 기간 / 장소 / 목적 입력 │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│  1. Understand               │
│  출장 목적과 상황 이해       │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│  2. Plan                     │
│  필요한 업무 / 자료 판단     │
│  최적 출장 계획 수립         │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│  3. Act                      │
│  예약 / 등록 / 일정 실행     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│  4. Prepare                  │
│  목적별 출장 준비자료 생성   │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│  5. Support                  │
│  출장 중 지원 / 후속관리     │
└──────────────────────────────┘
```

Find Your Partners의 핵심은 **모든 기능을 무조건 실행하지 않는 것**입니다.

AI가 출장 목적과 상황을 분석하여  
**필요한 업무만 선택하고 실행합니다.**

---

# 4. Example User Request

```text
8월 30일에 서울 코엑스로 인터배터리 박람회 출장 준비를 해줘.

출장 목적은 고객들을 만나 교류하고,
파트너십을 강화하기 위함이야.
```

AI Agent는 위 요청으로부터 다음 정보를 추출합니다.

| 항목 | 추출 정보 |
|---|---|
| 출장일 | 8월 30일 |
| 출장지 | 서울 코엑스 |
| 출장 유형 | 박람회 참관 |
| 행사 | InterBattery |
| 주요 목적 | 고객 교류 |
| Business Goal | Partnership 강화 |
| 필요한 업무 | 출장 등록, 이동계획, 일정등록, 행사/기업 조사, 출장 Brief 작성 |

---

# 5. AI Agent Decision Making

## 5.1 출장 상황 분석

AI Agent는 사용자의 요청을 분석하여 출장에 필요한 Task를 생성합니다.

```text
출장 목적 이해
      ↓
출장 유형 분류
      ↓
출장지 / 일정 분석
      ↓
필요 업무 결정
      ↓
필요 Tool 선택
      ↓
Action 실행
```

---

## 5.2 교통수단 자동 판단

AI가 출장 거리, 일정, 비용, 이동시간 등을 고려하여 적절한 이동수단을 판단합니다.

```text
출장지 분석
    │
    ├─ 가까운 국내 출장
    │      └─ 차량 / 기차 검토
    │
    ├─ 장거리 국내 출장
    │      └─ 기차 / 항공 비교
    │
    └─ 해외 출장
           ├─ 항공편
           ├─ 공항 이동
           ├─ 현지 교통
           └─ 렌터카 필요 여부 판단
```

판단 기준 예:

- 출장 거리
- 이동시간
- 출장 일정
- 미팅 시작시간
- 비용
- 사내 출장 규정
- 예약 가능 여부
- 사용자의 선호

---

## 5.3 숙박 필요 여부 판단

예:

```text
당일 출장
→ 호텔 예약 X

2일 이상 출장
→ 호텔 후보 탐색

고객사 방문 중심
→ 고객사 접근성이 높은 호텔 우선

늦은 시간 공항 도착
→ 공항 접근성을 고려한 호텔 선택
```

---

# 6. Automatic Actions

AI Agent는 판단 결과를 바탕으로 필요한 Tool/API를 호출합니다.

## 출장 행정

- 출장 시스템 신청서 자동 작성
- 출장 기간 등록
- 출장 목적 작성
- 예상 출장비 작성
- 결재 요청

## 교통

- 항공권 검색 및 예약
- KTX / SRT 검색 및 예약
- 렌터카 예약
- 공항 이동수단 추천
- 현지 교통 계획

## 숙박

- 호텔 필요 여부 판단
- 출장 규정 기반 호텔 검색
- 위치 / 일정 기반 최적 호텔 추천
- 호텔 예약

## Calendar

- 출장 일정 생성
- 이동시간 Block 생성
- 고객 미팅 등록
- 박람회 일정 등록
- Reminder 설정

---

# 7. ⭐ 핵심 차별화 기능 — 출장 준비자료 자동 생성

Find Your Partners의 가장 중요한 차별점입니다.

AI는 사용자가 별도로

> "출장 준비자료도 만들어줘."

라고 요청하지 않아도 됩니다.

Agent가 **출장 목적을 분석하고 출장 성공에 필요한 자료가 무엇인지 스스로 판단하여 생성**합니다.

---

# 8. Purpose-based Business Consulting

출장 목적에 따라 AI가 서로 다른 Research / Analysis Workflow를 수행합니다.

---

## 8.1 박람회 / 전시회 출장

예:

```text
InterBattery 참관
+
고객 교류
+
Partnership 강화
```

AI는 단순 행사 정보를 제공하지 않고 **출장 목적 달성을 위한 Business Consulting**을 수행합니다.

### Research

- 박람회 개요
- 주요 산업 Trend
- 참가기업 전체 List
- 기존 고객사 참가 여부
- 경쟁사 참가 여부
- 잠재 Partner 후보
- 기업별 주요 제품 / 기술
- 최근 기업 동향
- 부스 위치

### Analysis

AI는 참가기업을 다음 관점에서 평가합니다.

```text
당사 사업과의 연관성
+
기존 고객 관계
+
기술 경쟁력
+
Partnership 가능성
+
신규 Business Opportunity
+
최근 기업 동향
```

### Priority Example

| 기업 | 관계 | 주요 기술 | Partnership 가능성 | 방문 우선순위 |
|---|---|---|---:|---:|
| A기업 | 기존 고객 | EV Battery Module | 높음 | 1 |
| B기업 | 잠재 Partner | BMS | 매우 높음 | 2 |
| D기업 | 신규 업체 | Thermal Solution | 높음 | 3 |
| C기업 | 경쟁사 | Battery Pack | 참고 | 4 |

### Visit Route Optimization

Priority와 부스 위치를 함께 고려합니다.

```text
A기업
  ↓
B기업
  ↓
D기업
  ↓
C기업
```

---

# 9. InterBattery Business Brief

AI가 최종적으로 생성하는 출장 준비자료 예시입니다.

## InterBattery Business Opportunity Brief

### 1. 행사 Overview

- 행사 개요
- 주요 전시 분야
- 산업 핵심 Trend

### 2. 주요 참가기업

- 기존 고객
- 경쟁사
- 신규 Partner 후보
- 기술 유망기업

### 3. Business Opportunity

- 신규 Partnership 가능 기업
- 신규 기술 Opportunity
- 잠재 고객
- 사업 확장 가능 영역

### 4. 방문 Priority

```text
Priority 1
기존 핵심 고객

Priority 2
Partnership 가능성이 높은 기업

Priority 3
신규 Business Opportunity 기업

Priority 4
시장 / 경쟁 Trend 파악 대상
```

### 5. 최적 방문 동선

기업 Priority + 부스 위치 + 일정 기반 최적 Route

### 6. 기업별 Meeting Brief

- 회사 Overview
- 최근 동향
- 주요 기술
- 관심사항
- Discussion Point
- 예상 질문
- Partnership 제안 Point

### 7. 최종 출장 Schedule

- 이동
- 박람회
- 고객 미팅
- 기업 방문
- 복귀

---

# 10. Customer Meeting Scenario

출장 목적이 고객 미팅이라면 AI는 다른 준비자료를 생성합니다.

### Research

- 고객사 최근 사업 동향
- 최근 실적
- 신규 Project
- 주요 제품 / 기술
- 경쟁사 관계
- 산업 Trend
- 최근 뉴스
- 과거 미팅 자료
- 기존 Action Item

### Generated Brief

```text
Customer Executive Summary
        ↓
최근 주요 동향
        ↓
고객 관심사항
        ↓
기존 협업 현황
        ↓
주요 Discussion Point
        ↓
예상 Q&A
        ↓
제안 가능 아이템
        ↓
Partnership Opportunity
```

---

# 11. Other Business Trip Scenarios

## Supplier / Partner Visit

AI가 준비할 수 있는 정보:

- 공급사 현황
- 가격 및 원자재 동향
- 공급 Risk
- 경쟁 공급사 비교
- 품질 이슈
- 과거 협의사항
- 협상 Point
- Action Item

## Factory Visit

AI가 준비할 수 있는 정보:

- 공장 Overview
- 생산 제품
- 생산능력
- 주요 공정
- 품질 이슈
- 개선과제
- 방문 체크 Point
- Meeting Agenda

---

# 12. System Architecture

```text
                           ┌─────────────────────┐
                           │        USER         │
                           │   자연어 출장 요청  │
                           └──────────┬──────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │      AI AGENT CORE      │
                         │                         │
                         │ Understand → Plan → Act │
                         └────────────┬────────────┘
                                      │
             ┌────────────────────────┼─────────────────────────┐
             │                        │                         │
             ▼                        ▼                         ▼
    ┌────────────────┐      ┌─────────────────┐       ┌─────────────────┐
    │ Planning Agent │      │  Action Agent   │       │ Research Agent  │
    │                │      │                 │       │                 │
    │ Task Planning  │      │ Tool / API Call │       │ Web / DB Search │
    │ Decision       │      │ Booking         │       │ Company Research│
    └────────┬───────┘      └────────┬────────┘       └────────┬────────┘
             │                       │                          │
             └───────────────────────┼──────────────────────────┘
                                     │
                                     ▼
                          ┌──────────────────────┐
                          │   Report Generator   │
                          │                      │
                          │ Business Trip Brief  │
                          └──────────────────────┘
```

---

# 13. External Tools / APIs

## Internal Systems

- 출장 시스템
- ERP / 그룹웨어
- 전자결재
- Outlook / Google Calendar
- 고객 / Partner DB
- 기존 출장 보고서
- 사내 회의록
- Knowledge Base

## External APIs

- 항공권 API
- 기차 / 교통 API
- 호텔 API
- 렌터카 API
- 지도 / 경로 API
- 날씨 API
- 환율 API
- 행사 / 전시회 정보 API
- 기업정보 API
- 뉴스 / 검색 API

---

# 14. Core AI Technologies

## Natural Language Understanding

출장 요청에서 핵심 정보를 추출합니다.

```json
{
  "date": "2026-08-30",
  "location": "서울 코엑스",
  "event": "InterBattery",
  "trip_type": "exhibition",
  "business_goal": [
    "고객 교류",
    "Partnership 강화"
  ]
}
```

---

## Agent Planning

Goal을 Sub-task로 분해합니다.

```text
Goal

InterBattery에서
고객 관계 강화 및 신규 Partner 발굴

↓

Tasks

1. 출장 행정 처리
2. 이동수단 결정
3. 일정 생성
4. 참가기업 조사
5. 고객사 식별
6. Partner 후보 분석
7. 방문 Priority 결정
8. 방문 동선 최적화
9. Business Brief 생성
```

---

## Tool Selection

Agent가 상황에 맞는 Tool만 선택합니다.

```text
Flight Tool
→ 해외 / 장거리 출장

Train Tool
→ 국내 철도 이동이 효율적인 경우

Hotel Tool
→ 숙박이 필요한 경우

Calendar Tool
→ 출장 / 미팅 일정 생성

Search Tool
→ 박람회 / 고객 / 산업 조사

Report Tool
→ 출장 목적별 자료 생성
```

---

## Research & Reasoning

검색 결과를 단순 요약하는 것이 아니라 여러 정보를 종합하여 의사결정을 수행합니다.

```text
기업 사업영역
+
당사 사업 연관성
+
고객 / Partner 관계
+
기술 경쟁력
+
최근 사업 동향
+
부스 위치
+
출장 목적

↓

기업 방문 Priority
```

---

## Report Generation

결과를 실제 출장자가 사용할 수 있는 형태로 생성합니다.

지원 예정 형식:

- Markdown
- PDF
- PowerPoint
- Excel
- Business Brief
- Executive Summary

---

# 15. Existing System vs Find Your Partners

| 기존 출장 시스템 | Find Your Partners |
|---|---|
| 사용자가 업무를 판단 | **AI가 필요한 업무를 판단** |
| 사용자가 교통수단 선택 | **AI가 최적 이동수단 판단** |
| 출장 신청 중심 | **출장 성공 중심** |
| 정형화된 입력 | **자연어 요청** |
| 예약 / 행정 자동화 | **판단 + 실행 + Consulting** |
| 출장자료 직접 작성 | **목적별 출장자료 자동 생성** |
| 시스템별 개별 이용 | **Agent가 Tool 통합 Orchestration** |
| 출장 전 업무 중심 | **출장 전·중·후 End-to-End 지원** |

---

# 16. Expected Value

### ⏱ 출장 준비시간 절감

여러 사이트와 시스템을 직접 확인하는 시간을 최소화합니다.

### 🤖 판단 업무 자동화

단순 RPA가 아니라 상황을 이해하여 Agent가 필요한 업무를 선택합니다.

### ✅ 준비 누락 최소화

예약, 출장 등록, 캘린더, 미팅 자료 등을 통합 관리합니다.

### 🎯 목적 맞춤형 출장 준비

출장 목적에 따라 전혀 다른 Research와 Brief를 제공합니다.

### 🤝 Business Opportunity 확대

고객 / Partner / 신규 기업 정보를 분석하여 사업기회를 발굴합니다.

### 📈 출장 성과 향상

궁극적인 목표는 출장 행정 자동화가 아니라 **출장의 Business Outcome 개선**입니다.

---

# 17. Hackathon MVP

3인 팀 Hackathon을 고려하여 핵심 Agent Experience에 집중합니다.

## MVP Features

- [ ] 자연어 출장 요청
- [ ] 출장 정보 자동 추출
- [ ] 출장 목적 분류
- [ ] Agent Task Planning
- [ ] 교통수단 필요 여부 판단
- [ ] 숙박 필요 여부 판단
- [ ] 출장 등록 Mock API
- [ ] 교통 예약 Mock API
- [ ] Calendar 일정 생성
- [ ] Web 기반 행사 / 기업 조사
- [ ] 고객 / Partner 후보 분석
- [ ] 기업 방문 Priority 생성
- [ ] 방문 동선 생성
- [ ] Business Trip Brief 자동 생성
- [ ] Agent 실행 과정 Visualization

---

# 18. Recommended Multi-Agent Structure

```text
Supervisor Agent
      │
      ├── Travel Planning Agent
      │      ├─ 이동수단 판단
      │      ├─ 숙박 판단
      │      └─ 일정 설계
      │
      ├── Action Agent
      │      ├─ 출장 등록
      │      ├─ 예약
      │      └─ Calendar
      │
      ├── Research Agent
      │      ├─ 박람회 조사
      │      ├─ 기업 조사
      │      ├─ 고객 조사
      │      └─ 산업 Trend 조사
      │
      └── Business Consulting Agent
             ├─ Priority 분석
             ├─ Opportunity 분석
             ├─ 방문 전략
             └─ 출장 Brief 생성
```

---

# 19. Demo Scenario

## User

```text
8월 30일에 서울 코엑스로 인터배터리 박람회 출장 준비를 해줘.

출장 목적은 고객들을 만나 교류하고,
파트너십을 강화하기 위함이야.
```

## Agent — Understand

```text
출장 유형: 박람회 참관

핵심 목적:
- 기존 고객 관계 강화
- 신규 Partner 발굴
- Business Opportunity 탐색
```

## Agent — Plan

```text
✓ 출장 등록 필요
✓ 이동수단 결정 필요
✓ Calendar 일정 등록 필요
✓ InterBattery 조사 필요
✓ 참가기업 분석 필요
✓ 고객사 / Partner 후보 분석 필요
✓ 방문 Priority 결정 필요
✓ 출장 Brief 생성 필요
```

## Agent — Act

```text
✓ 출장 신청서 작성
✓ 교통수단 조회
✓ 기차 예약
✓ Calendar 등록
✓ 박람회 참가기업 정보 수집
✓ 기업 최신 동향 조사
✓ Partner 후보 분석
✓ 방문 동선 생성
✓ 출장 Brief 생성
```

## Result

```text
출장 준비 완료

━━━━━━━━━━━━━━━━━━━━

🚆 교통
KTX 예약 완료

📅 일정
Calendar 등록 완료

🏢 Priority 기업
1. A기업
2. B기업
3. D기업
4. C기업

🗺 추천 방문 동선
A → B → D → C

📑 출장자료
InterBattery Business Opportunity Brief 생성 완료
```

---

# 20. Success Metrics

| Category | KPI |
|---|---|
| 업무 효율 | 출장 준비시간 감소 |
| 자동화 | 사용자 직접 처리 단계 감소 |
| 정확도 | 출장 준비 누락 감소 |
| Agent | 자동 의사결정 Task 비율 |
| 정보 가치 | 추천 정보 활용도 |
| Business | 신규 Partner / Opportunity 발굴 |
| UX | 사용자 만족도 |

---

# 21. Vision

기존 출장 프로세스:

```text
출장 계획
   ↓
예약
   ↓
출장
```

Find Your Partners:

```text
출장 목적 이해
      ↓
성공 조건 분석
      ↓
필요 업무 판단
      ↓
예약 / 등록 자동 실행
      ↓
기업 / 시장 정보 조사
      ↓
출장 목적별 Business Consulting
      ↓
맞춤형 출장자료 생성
      ↓
최적 일정 / 미팅 전략 제안
      ↓
출장 수행 지원
      ↓
출장 결과 Knowledge 축적
```

---

# 22. Key Message

> ## AI가 출장 목적을 이해하고, 필요한 행동을 스스로 판단·실행하며, 출장 성공에 필요한 정보와 전략까지 준비한다.

### **From Trip Preparation to Business Success**

Find Your Partners는  
**단순한 출장 업무 자동화를 넘어 출장의 성과를 높이는 AI Business Trip Agent**를 목표로 합니다.
