---
# the default layout is 'page'
icon: fas fa-info-circle
order: 5
---

## Full-Stack Engineer

운영 중인 금융기관 시스템의 장애 원인을 찾고 고쳐 온 Java 백엔드 개발자입니다. 금융기관 고객사에 상주하며 고객사 요청을 받아 Java/Spring Boot·React 코드를 고치고, 배포하고, 서버를 점검했습니다. 에러 로그가 남지 않는 장애는 패킷과 라우팅까지 따라가 원인을 특정했습니다. 그 전에는 공공·유통 EAI 환경에서 기관 간 연동 오류를 처리했습니다.

최근에는 FastAPI, SQLAlchemy, LangGraph를 활용한 AI 에이전트 개발로 영역을 넓히고 있으며, 이 블로그에는 그 과정에서 정리한 프로젝트와 기술 글을 올립니다.

경력 5년 1개월

## Career

### 엠피씨플러스 · DT본부 IT서비스개발팀 · 대리

2026.04.06 - 2026.06.26 (약 3개월) · 정규직 · 풀스택 개발자

**고객센터 상담 시스템 구축 및 개발, 운영** (2026.04.06 - 2026.06.26, 발주처: 전자제조·면세유통·외식 프랜차이즈 등 다수 고객사)

- CTI·TeleWeb·WebSocket 연동 분석 및 Linux 운영 지원
- AICC 구성 요소와 실시간 메시징 흐름을 분석하고 개발 서버를 구축
- JSP/Vue.js 화면, PostgreSQL/PostgREST 기반 서비스, OpenResty 프록시와 n8n 자동화를 개발·설정
- 사용자 권한과 CTI 설정을 정리하고 운영 이슈의 원인 분석 및 안정화를 지원
- 기술: Java, Spring Boot, JSP, Vue.js, WebSocket, PostgreSQL, PostgREST, OpenResty, n8n, Linux, SVN

### 쿠도커뮤니케이션 · AX사업부 AX서비스개발팀 · 대리

2024.05.01 - 2026.03.06 (1년 10개월) · 정규직 · 오픈소스 취약점 관리 시스템 운영 및 유지보수

**오픈소스 취약점 관리 시스템 운영·유지보수 — 금융기관 2곳(은행, 생명보험사)** (2024.12 - 2026.03)

팀이 맡은 금융기관 고객사 중 은행과 생명보험사 두 곳의 운영을 담당했고, 두 곳의 장애 대응에 가장 많은 시간을 썼습니다.

- 고객사 요청을 분석해 Java(Spring Boot)·React 코드를 수정하고 배포
  - Java: 분석 ID가 비어 들어올 때 URL의 analysisId를 쓰도록 보완, 담당자 현행화 로직 수정, 결재자 검증 로직 수정
  - React: 자가 점검 안내 메시지 수정, 현황 알림 메뉴 정리 등 화면 작업
- 서버 정기 점검, 고객사 담당자 응대
- Docker 기반 서비스 운영 및 장애 대응
- 기술: Java, Spring Boot, React, TypeScript, Docker, Linux, Git, Bitbucket, Nexus Repository

**장애 사례 1 — 에러 로그 없는 간헐적 접속 장애**

특정 내부망 사용자만 접속이 끊기는데 애플리케이션 로그에는 예외가 없었습니다. tcpdump로 요청(SYN)은 도착하지만 응답(SYN-ACK)이 나가지 않는 것을 확인했고, 라우팅 테이블에서 Docker가 자동 할당한 대역이 고객사 내부망과 겹쳐 응답이 Docker bridge로 나가는 것을 찾았습니다. 재시작 없이 적용되는 정적 라우트로 복구했고, 근본 대책으로 Docker 주소 풀을 내부망과 겹치지 않게 지정하는 방안을 정리했습니다.

**장애 사례 2 — 예외 없이 결과만 비던 저장소 반입 실패**

Nexus Repository에서 분석 대상 파일을 가져오는 과정이 특정 조건에서만 실패했고, 예외 없이 분석 결과만 누락됐습니다. 요청 → 수신 → 저장 → 후속 처리로 구간을 나눠 성공·실패 로그를 비교해 원인 지점을 특정했고, 이를 본사 개발 담당자에게 전달해 수정이 반영됐습니다.

### 누리꿈소프트 · 혁신사업부 DX개발팀 · 프로

2023.08.07 - 2024.04.12 (8개월) · 정규직 · 풀스택 개발자

**MSA기반 야드비상조업 시스템** (2023.08.07 - 2023.12.31, 발주처: 제조업체(철강) A)

- MSA 기반 제조 운영 시스템(야드비상조업 시스템) 웹 개발
- 기술: HTML5, CSS3, JavaScript, Java, JSP

**실시간 데이터 플랫폼 구축** (2024.01.17 - 2024.02.29, 발주처: 카드사(금융))

- Oracle 변경 데이터를 Kafka로 전달하는 흐름에서 Single Message Transform 소스를 반영하고 변환 결과를 확인
- 기술: Apache Kafka, Oracle GoldenGate for Big Data, Oracle, Java

**REST API 문서 자동화** (2024.03 - 2024.04, 발주처: 제조업체(철강) B)

- JUnit 테스트와 Spring REST Docs를 연계해, 테스트를 통과해야 API 문서가 생성되는 체계 구축
- 기술: Java, Spring Boot, REST Docs

### 이썸테크 · 서비스사업본부 서비스개발팀 · 사원

2022.05.11 - 2023.05.31 (1년 1개월) · 정규직 · EAI 솔루션 구축 및 유지보수

**동물검역 수입 전자검역증 시스템** (2022.06.01 - 2023.03.02, 발주처: 공공기관(검역 분야))

- 호주 수입 전자검역증 화면 웹 개발, 기존 뉴질랜드 수입 전자검역증 유지보수
- 기술: HTML5, CSS3, JavaScript, jQuery, Java, XML, JSP, Tibero, SVN, AIX

**클라우드 EDI** (2023.03.03 - 2023.03.30, 발주처: 유통·IT 기업)

- 기술: HTML5, CSS3, JavaScript, jQuery, Java, XML, JSP, SVN, AWS

**eSCM 구축** (2023.03.31 - 2023.05.31, 발주처: 농업 유통 관련 기관)

- eSCM 웹 개발
- 기술: HTML5, CSS3, JavaScript, Nexacro, Java, JSP, SVN, ozReport

기관·기업 시스템 간 데이터 구조와 인터페이스를 확인하며 연동 오류와 유지보수 이슈를 처리했습니다.

### 엘비휴넷 · 기술팀 · 일반SD

2020.08.28 - 2021.08.31 (1년) · 정규직

**고객 기술지원**

- 통신사 인터넷, TV, 인터넷 전화, IoT 상품에 대한 장애 기술 상담 및 IoT 상품 마케팅
- 고객 환경과 증상을 단계적으로 확인해 원인을 좁히고 점검·조치 순서를 안내
- 고객에게 기술 이슈를 이해하기 쉬운 언어로 설명하고 요청사항을 구조화
- 기술: 고객 커뮤니케이션, 장애 진단, 원격 기술지원

## Tech Stack

| 분야 | 기술 |
| --- | --- |
| Backend | Java, Spring Boot, JSP, REST API, Python, FastAPI, SQLAlchemy |
| AI | LangGraph, LangChain, RAG, pgvector, MCP |
| Frontend | React, TypeScript, Next.js, JavaScript, Vue.js, jQuery |
| Database | PostgreSQL, MySQL, MariaDB, Oracle, Tibero, MongoDB |
| Integration | EAI, WebSocket, CTI |
| Infrastructure | Linux (CentOS, Rocky Linux), AIX, Docker, Nexus Repository, OpenResty, n8n |
| Data | Kafka, Snowflake, Hadoop·Spark(교육 과정) |
| Testing / Docs | JUnit, Spring REST Docs, pytest |
| Collaboration | Git, SVN, Bitbucket, JIRA |

## Engineering Focus

**장애 원인 추적**

- 애플리케이션 로그에 흔적이 없으면 패킷·라우팅 등 아래 계층으로 범위를 옮겨 원인을 좁힙니다.
- 구간을 나눠 성공·실패 로그를 비교해 값이 달라지는 지점을 찾습니다.
- 복구에서 끝내지 않고, 같은 장애가 다시 생기지 않도록 근본 대책을 정리합니다.

**운영 중인 시스템 유지보수**

- 고객사 요청을 분석해 코드를 고치고, 배포하고, 정기 점검을 합니다.
- 고객사 담당자와 직접 소통하며 요청 범위와 영향을 확인합니다.

**검증 가능한 구조**

- 테스트를 통과해야 생성되는 API 문서(Spring REST Docs)
- LLM 응답을 골든셋으로 측정하는 회귀 테스트

## Education

- **전주대학교** 영어교육과 (상담심리학과 복수전공) (2014.03 - 2020.08, 졸업)

### Training

| 교육기관 | 교육명 | 기간 | 시간 |
| --- | --- | --- | --- |
| 퍼스트존 아카데미 학원 | 한화 내일 아카데미 ICT부문 — [지능형(AI) 에이전트 기반 서비스 개발](https://knda-hanwhasystems.com/) (서울2회차) | 2026.09.01 - 2026.11.13 | 400시간 |
| K-ICT 빅데이터센터 | 데이터·AI 활용 역량강화과정 | 2025.04.12 - 2025.04.26 | 14시간 |
| 인공지능산업융합사업단 | 풀스택 엔지니어 역량 기초 이해하기 | 2024.08.21 - 2024.08.23 | 20시간 |
| 수도권ICT이노베이션스퀘어 | 중급 데이터 엔지니어링 | 2024.07.22 - 2024.09.19 | 160시간 |
| 수도권ICT이노베이션스퀘어 | 중급 데이터 분석 | 2024.07.22 - 2024.08.19 | 160시간 |
| 패스트캠퍼스 | 나도 할 수 있는 Java&Spring 웹 개발 종합반 | 2023.12.27 - 2024.02.21 | 65시간 |
| 한국스마트정보교육원 | 디지털컨버전스 융합 SW개발자 양성과정D | 2021.11.15 - 2022.04.28 | 896시간 |

현재 진행 중인 한화 내일 아카데미 과정의 학습 기록은 [Naver 블로그](https://blog.naver.com/dldl8819)와 [GitHub](https://github.com/dldl8819/hanwha-ai-agent-academy)에 정리하고 있습니다. 서울 홍대점(마포구 월드컵북로4길 77, 3층 · 홍대입구역 2번 출구 도보 5분)에서 진행됩니다.

## Certifications

- SnowPro Core Certification (2025.02)
- MongoDB Certified Associate DBA (2024.09)
- MongoDB Certified Associate Developer (2024.06)
- 전문상담교사 2급 (2020.08)
- 중등학교 2급 정교사(영어) (2020.08)

## Language

- 영어: 비즈니스 레벨 (OPIc IM1, 2026.03.15)

## Activities

- **[가이드런 프로젝트](https://about.guiderun.org/)** — 2025.08부터 가이드러너이자 서포터즈로서, 시각장애 러너와 가이드 러너의 안전한 훈련을 지원하고 있습니다. 팀 운영과 현장 상황 대응을 통해 협업 능력과 책임감을 키웠습니다.
- **[헤이팸](https://www.heifam.co.kr/)** — 스타크래프트 빠른무한 3:3 커뮤니티를 운영하다가, 팀 밸런스 문제를 직접 해결하기 위해 웹 서비스까지 개발했습니다. ([자세히 보기](/projects/))

## 연락처

- GitHub: [dldl8819](https://github.com/dldl8819)
- Email: heiminsik@gmail.com
- Naver 블로그: [blog.naver.com/dldl8819](https://blog.naver.com/dldl8819) — 운동·자기관리 기록과 개발 학습/트러블슈팅 경험을 함께 정리하며, 꾸준한 기록으로 자기관리와 학습 습관을 유지하고 있습니다.
