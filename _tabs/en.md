---
title: CV (EN)
icon: fas fa-file-lines
order: 6
layout: page
permalink: /en/
---

## Minsik Lee — Backend / Full-Stack Engineer

Seoul, South Korea · [heiminsik@gmail.com](mailto:heiminsik@gmail.com) · [github.com/dldl8819](https://github.com/dldl8819)

Backend-leaning full-stack engineer with 5+ years of professional experience, 4 of them in software development, across financial, manufacturing, and public-sector systems. Java/Spring Boot and React/TypeScript on Linux and Docker. Consistently the person who takes an intermittent production failure and finds the actual cause — container networking, repository integration, request-path behavior — instead of patching the symptom. Currently completing a 400-hour AI agent development program (FastAPI, SQLAlchemy, LangChain).

> The rest of this site is written in Korean. This page is the English summary.
{: .prompt-info }

## Selected Strengths

- **Root-cause debugging.** Traced an intermittent connection failure, with nothing in the application logs, to a Docker network CIDR collision using packet and routing analysis, then restored TCP flow with a static route. Pinpointed where artifact ingestion from a Nexus Repository silently failed by comparing success and failure logs stage by stage, and handed the finding to the headquarters developer who fixed the product code.
- **Reviewing code for what it leaks, not just what it returns.** Framework defaults are frequently unsafe: a FastAPI validation error echoes the submitted request body, including the password, so I replaced it with a handler that returns field names only. Applied the same review habit to HTML escaping of database-sourced values and to auth errors that reveal whether an account exists.
- **Verifiable documentation and tests.** Wired JUnit test results into Spring REST Docs so API documentation fails the build when behavior changes. Maintain detailed public engineering notes explaining design decisions and failure analysis.

## Experience

### MPC Plus — Engineer, DT Division

2026.04 – 2026.06 · Contact-center (AICC) platform development and operations

- Analyzed CTI and WebSocket real-time messaging flows and stood up the development environment.
- Built JSP/Vue.js screens, PostgreSQL/PostgREST services, OpenResty proxying, and n8n automation.

### Cudo Communication — Engineer, AX Service Development

2024.05 – 2026.03 · Operations and maintenance of an open-source vulnerability management system at two financial institutions (a bank and a life insurer)

- Worked on site at client institutions: analyzed client requests, changed Java (Spring Boot) business logic and React screens, and deployed the fixes.
- Ran routine server checks and handled day-to-day contact with client staff.
- Handled incident response on Docker/Linux, including the two incidents described above (Docker CIDR collision, Nexus ingestion failure).

### Nuriggum Soft — Engineer, DX Development

2023.08 – 2024.04

- Automated REST API documentation with JUnit and Spring REST Docs, so documentation is only generated when tests pass.
- Applied and verified a Single Message Transform for Oracle-to-Kafka change data streaming at a card issuer.
- Built web screens for an MSA-based manufacturing operations system for a steel manufacturer.

### Esum Tech — Engineer, Service Development

2022.05 – 2023.05 · EAI integration delivery and maintenance

- Delivered EAI-based web systems for a public quarantine agency, a retail/IT enterprise, and an agricultural distribution body (Java, JSP, jQuery, Tibero, AIX, AWS).
- Analyzed cross-system interfaces and data structures to resolve integration defects.

### LB Hunet — Technical Support, Technical Team

2020.08 – 2021.08

- Diagnosed internet, IPTV, and IoT faults for a telecom carrier's customers, narrowing causes through structured elimination and explaining them in plain language.

## Technical Skills

| Area | Stack |
| --- | --- |
| Languages | Java, TypeScript, JavaScript, Python, SQL |
| Backend | Spring Boot, FastAPI, JSP, REST API design |
| Frontend | React, Next.js, Vue.js |
| Data | PostgreSQL, Oracle, MySQL/MariaDB, Tibero, MongoDB, Kafka, Snowflake |
| Infrastructure | Docker, Linux (CentOS/Rocky), Nexus Repository, Git, SVN |
| Testing / Docs | JUnit, pytest, Spring REST Docs |
| Integration | EAI, WebSocket |

## Side Project

**[Heifam](https://www.heifam.co.kr/)** — team-balancing and match-record service for a StarCraft community, built solo and running in production. Next.js/TypeScript front end, Spring Boot API, Supabase (PostgreSQL). Evaluates every possible team combination to minimize rating gap, updates ratings with an ELO algorithm from match results, and derives per-player and per-composition statistics. ([source](https://github.com/dldl8819/heifam))

## Education & Certifications

- Hanwha Tomorrow Academy — AI Agent Service Development, 400 hours (2026.09 – 2026.11, in progress)
- Jeonju University — B.A. in English Education, double major in Counseling Psychology (2020)
- SnowPro Core (2025) · MongoDB Certified Associate DBA (2024) · MongoDB Certified Associate Developer (2024)

## Languages & Availability

Korean (native). English: intermediate — comfortable reading technical material and writing code reviews and documentation.

Available as a remote contractor on flexible hours, based in KST (UTC+9).
