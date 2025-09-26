<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>

# 🐬MySQL - [📥](Download.md)

---

## MySQL?
```java
- MySQL은 대표적인 관계형 데이터베이스 관리 시스템(RDBMS)
- 데이터를 표(테이블) 형식으로 관리하며, **SQL(Structured Query Language)**을 사용
- 오픈소스 기반이었고 지금은 Oracle이 관리 (무료/상용 버전 모두 있음)
- 웹 서비스, ERP, CMS, 게임 서버 등 전 세계에서 가장 많이 사용되는 DBMS 중 하나
```
## ⚙️ MySQL 주요 특징
-오픈소스 & 무료 (Community Edition) - 현재 `Oracle`에서 관리
-크로스 플랫폼 (`Windows`, `Linux`, `Mac` 모두 지원)
-속도와 안정성이 높음
-대규모 서비스(예: Facebook, Twitter 초기)에도 사용됨
-다양한 클라이언트 툴 지원: `DBeaver`, `Workbench`, `phpMyAdmin` 등 (현재 `DBeaver`로 수업중)

## 📦 핵심 개념
- `Database (DB)` : 데이터의 모음
- `Table` : DB 안의 실제 데이터 저장 구조 (행=Row, 열=Column)
- `Primary Key (PK)` : 테이블의 고유 식별자
- `Foreign Key (FK)` : 다른 테이블과의 연결 키
- `SQL 문법` : DB 조작을 위한 언어

---

## 🖥️ 기본 명령어 (DDL, DML)

### 데이터베이스
```sql
CREATE DATABASE testdb;  -- 생성
USE testdb;              -- 선택
SHOW DATABASES;          -- 목록 확인
DROP DATABASE testdb;    -- 삭제
```
### 테이블
```sql
CREATE TABLE users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  user_name VARCHAR(100) NOT NULL,
  user_email VARCHAR(100) UNIQUE,
  reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

SHOW TABLES;   -- 테이블 목록
DESC users;    -- 테이블 구조 확인
DROP TABLE users; -- 테이블 삭제
```

### 데이터 조작
```sql
-- 입력
INSERT INTO users (user_name, user_email) 
VALUES ('김길동', 'Kim@test.com');

-- 조회
SELECT * FROM users;
SELECT user_name, user_email FROM users WHERE user_id = 1;
SELECT * FROM users ORDER BY reg_date DESC LIMIT 5;

-- 수정
UPDATE users SET user_email = 'new@test.com' WHERE user_id = 1;

-- 삭제
DELETE FROM users WHERE user_id = 1;
```

---

## 📜자주 쓰는 SQL 키워드 정리
| 키워드 | 설명 |
|-------|------|
|`CREATE` | DB, 테이블 생성|
|`DROP` | 삭제|
|`ALTER` | 테이블 구조 변경|
|`INSERT` | 데이터 입력|
|`SELECT`	|데이터 조회|
|`UPDATE`|	데이터 수정|
|`DELETE`|	데이터 삭제|
|`JOIN`|	여러 테이블 연결 조회|
|`WHERE`|	조건 지정|
|`ORDER BY`|	정렬|
|`GROUP BY`|	그룹화|
|`HAVING`	|그룹 조건|
|`LIMIT`|	조회 개수 제한|

---

**📝 요약**
1. **MySQL은 데이터를 테이블 형태로 관리하는 `DBMS`:** 오픈소스 `RDBMS`, `SQL` 사용
2. **핵심 구조:** `DB → Table → Row/Column`
3. **핵심 키워드:** `CREATE`, `SELECT`, `INSERT`, `UPDATE`, `DELETE`
4. **실무에서 자주 쓰는 것:**
- `SELECT + WHERE + ORDER BY + LIMIT`
- `INSERT` **/** `UPDATE` **/** `DELETE`
- `JOIN`, `GROUP BY`, `HAVING`
5. **집계 함수:** `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`
6. SQL을 사용해 데이터를 `CRUD`(`Create, Read, Update, Delete`)
7. **`JOIN`**과 `집계 함수`는 실무에서 **매우 중요**

**join 사용 예제**
```sql
-- users와 orders 테이블 조인
SELECT u.user_name, o.order_date, o.amount
FROM users u
JOIN orders o ON u.user_id = o.user_id;
```
**💡여러가지 `JOIN` 요약**
```
LEFT JOIN : 왼쪽(A) 다 가져오고, 오른쪽(B) 없는 건 NULL
RIGHT JOIN : 오른쪽(B) 다 가져오고, 왼쪽(A) 없는 건 NULL
INNER JOIN : 양쪽에서 공통되는 부분만
FULL OUTER JOIN : 양쪽 모두 다 (MySQL은 LEFT JOIN UNION RIGHT JOIN으로 구현)
```



---

<a href="#top" style="display:block; text-align:right; text-decoration:none; font-size:14px;">
⬆️ 맨 위로
</a>