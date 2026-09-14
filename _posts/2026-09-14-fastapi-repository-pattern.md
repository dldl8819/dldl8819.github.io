---
title: FastAPI에 리포지토리 패턴 적용하기
date: 2026-09-14 10:00:00 +0900
categories: [Backend, FastAPI]
tags: [fastapi, sqlalchemy, repository-pattern, architecture]
---

## 왜 필요한가

라우터에서 바로 DB에 접근하면 재사용·테스트·이관이 어려워진다. 특히 아래처럼 쿼리 조건을 f-string으로 직접 조립하면 SQL 인젝션에도 취약하다.

```python
# 안티패턴: 라우터에서 직접 SQL 조립
@router.get("/list")
def get_list(dept_id=None):
    sql = "SELECT * FROM documents WHERE 1=1"
    if dept_id:
        sql += f" AND dept_id = '{dept_id}'"
    session.execute(sql)
```

이 문제를 해결하기 위해 Router → Service → Repository → Model 로 계층을 나눴다.

```text
HTTP 요청
    |
Router        — 요청을 받아 분배
    |
Service        — 비즈니스 로직, 트랜잭션 경계
    |
Repository      — 쿼리 작성
    |
Model → DB
```

## Repository: 쿼리만 전담하는 계층

```python
from sqlalchemy import select, or_
from sqlalchemy.orm import Session, joinedload

def list_documents(
    session: Session,
    *,
    dept_id: str | None = None,
    q: str | None = None,
    limit: int = 50,
):
    stmt = select(Document)
    if dept_id:
        stmt = stmt.where(Document.dept_id == dept_id)
    if q:
        stmt = stmt.where(or_(Document.title.ilike(f"%{q}%")))
    stmt = stmt.options(joinedload(Document.dept)).limit(limit)
    return session.scalars(stmt).unique().all()
```

`select().where(...)`는 조건 값이 SQL 텍스트에 그대로 섞이지 않고 파라미터로 바인딩되기 때문에, 위의 f-string 조립 방식과 달리 인젝션에서 안전하다.

## Service: 트랜잭션 경계

서비스 함수 하나가 트랜잭션 하나의 단위다. 함수 안에서 리포지토리를 여러 번 호출해도, 전부 성공해야 commit되고 하나라도 실패하면 전체 rollback된다.

```python
@contextmanager
def session_scope():
    session = SessionLocal()
    try:
        yield session
        session.commit()
    except Exception:
        session.rollback()
        raise
    finally:
        session.close()
```

## 계층별 책임

| 계층 | 아는 것 | 모르는 것 |
| --- | --- | --- |
| Router | HTTP 요청/응답 | SQL, 트랜잭션 |
| Service | 비즈니스 규칙, 트랜잭션 경계 | SQL 문법 |
| Repository | 쿼리 작성법 | 이 결과로 뭘 판단할지 |
| Model | 테이블 구조 | 어떤 요청에서 쓰이는지 |

각 계층이 자기 바로 아래 계층만 호출하도록 지키면, DB를 SQLite에서 PostgreSQL로 바꾸거나 쿼리 조건이 하나 늘어나는 정도의 변경은 해당 계층만 손보면 끝난다.
