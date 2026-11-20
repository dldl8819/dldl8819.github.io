---
icon: fas fa-diagram-project
order: 3
layout: page
---

## 프로젝트

### [사내 IT 장애·문의 대응 AI Agent (ITssue)](https://github.com/issue-helpdesk/issue-helpdesk)

한화 내일 아카데미 ICT부문 캡스톤 프로젝트입니다. 반복되는 IT 문의는 AI가 1차로 응대하고, 해결이 어려운 건은 담당자에게 Jira 티켓을 자동으로 만들어 배정하는 헬프데스크 에이전트입니다. **'H-Agent Challenge 2026' 경진대회에서 최우수상**을 받았습니다.

- 기간: 2026.10 - 2026.11
- 역할: 6인 팀 팀장, 검색 담당
- 스택:
  - Backend: Python 3.12, FastAPI, SQLAlchemy 2, Alembic
  - AI: LangGraph, Claude API
  - 검색: PostgreSQL 17 + pgvector, 로컬 임베딩 BGE-M3
  - Frontend: React 19, TypeScript, Vite
  - 연동·배포: Jira Software(REST API, 웹훅), Docker Compose, Nginx, EC2
- 팀이 만든 기능:
  - **AI 상담**: 부족한 정보를 되묻고, 가이드 문서(RAG) → 과거 처리 이력 순으로 근거를 찾아 답변
  - **분류·긴급도 판단**: 7개 분류·50개 시나리오로 문의 유형과 긴급도를 판단하고, 문의자가 확인한 접수 초안으로 접수
  - **Jira 연동**: 티켓 생성과 담당자 자동 배정(부재 일정 반영), 웹훅과 주기 대조로 상태 동기화
  - **담당자·관리자 화면, 가이드 관리, 민감정보 보호**
- 내가 맡은 부분 (검색):
  - **임베딩 모델 비교·선정**: 평가셋 46문항으로 KURE-v1과 BGE-M3를 비교해 BGE-M3를 골랐습니다. 1위 적중률은 74% 대 59%였고, 리랭커는 1위 적중을 늘리지 못하면서 질문 하나에 31초가 걸려 넣지 않았습니다.
  - **권한 필터**: 열람 범위를 검색 SQL 조건으로 걸어, 범위 밖 문서가 결과와 근거 어디에도 나오지 않게 했습니다.
  - **근거 문장 선택과 전송 정책 필터**, 사용자 매뉴얼, 데이터셋 DB 스키마·시드 스크립트
- 회사·조직·데이터는 모두 가상 설정입니다.
- 코드: [github.com/issue-helpdesk/issue-helpdesk](https://github.com/issue-helpdesk/issue-helpdesk)

### [헤이팸 (Heifam)](https://www.heifam.co.kr/)

스타크래프트 빠른무한 3:3 내전 커뮤니티 "헤이팸"을 운영하며 반복되던 문제 — 팀 밸런스 불균형, 실력 차 불만, 기록 미누적, 운영진의 수기 관리 피로 — 를 직접 해결하기 위해 만든 서비스입니다. 구글 스프레드시트로 MMR을 관리하던 것에서 시작해, 자동 팀 편성 + ELO 기반 MMR + 통합 운영 플랫폼으로 발전시켰습니다.

- 상태: 운영 중, 서비스로 계속 발전시키는 중
- 역할: 커뮤니티 운영진 겸 개발자 (1인 개발)
- 스택:
  - Frontend: React, TypeScript, Next.js
  - Backend: Java, Spring Boot
  - Database: Supabase (PostgreSQL)
  - 배포: Vercel(프론트), Render(백엔드)
- 주요 기능:
  - **자동 팀 밸런스**: 참가자 6명의 모든 팀 조합 경우의 수를 계산해, MMR 차이가 최소인 조합을 자동 선택 (3v3)
  - **ELO 기반 MMR**: 초기 MMR은 기존 티어 기준으로 시작하고, 경기 결과를 입력하면 ELO 알고리즘으로 자동 갱신 — 플레이할수록 정확해지는 구조
  - **경기 입력 → 자동 반영**: 팀 구성·승리팀만 입력하면 MMR 갱신, 승/패 기록, 통계 반영까지 자동 처리
  - **개인 기록**: 총 경기수, 승/패, 승률, 최근 10경기, 연승/연패, MMR 변화 추이
  - **팀·종족 조합 통계**: 특정 3인 조합 승률, 종족 조합(PPP/PPT/PTZ 등) 매치업 승률, 최근 추세 분석
- 배운 점: 기능보다 중요한 건 운영진의 실제 편의성이었고, 데이터가 쌓일수록 체감 공정성이 확실히 올라갔습니다. 엑셀에서 시작했지만 복잡한 로직과 확장성을 생각하면 결국 웹 서비스로 가야 한다는 걸 체감한 프로젝트입니다.
- 코드: [github.com/dldl8819/heifam](https://github.com/dldl8819/heifam)
- 개발기: [엑셀에서 서비스로 — 헤이팸 팀 밸런스 시스템 개발기](/posts/heifam-team-balance-system/)
