<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>


# 🦫DBeaver - [📥](Download.md)

---

### DBeaver란?
```java
- 오픈소스 데이터베이스 관리 툴 DB Client / DB GUI Tool
- 다양한 데이터베이스(MySQL, MariaDB, PostgreSQL, Oracle, MongoDB, SQLite, SQL Server 등)에 한 번에 접속하고 관리할 수 있는 통합 도구.
- Windows, macOS, Linux 지원 크로스플랫폼.
- 무료 버전Community과 유료 버전Enterprise이 있음.
```

---


## 🐬MySQL / 🍃MongoDB 연결

### 🐬MySQL 연결 방법

>전제: MySQL 서버가 설치되어 있거나, Docker로 실행 중이어야 함
```java
1. 새 연결 만들기
- DBeaver 실행 → 상단 메뉴 Database → New Database Connection
- 검색창에 MySQL 입력 후 선택

2. 접속 정보 입력
- Host: localhost (또는 서버 주소)
- Port: 3306 (MySQL 기본 포트, Docker에서 -p 3307:3306 한 경우 → 3307)
- Database: 연결할 DB명(예: testdb, 없으면 비워도 됨)
- User: root (또는 사용자 계정)
- Password: 계정 비밀번호 입력

3. 드라이버 다운로드
- 처음 연결 시, JDBC 드라이버 다운로드 창이 뜸 → Download 클릭

4. 테스트 연결
- Test Connection → 성공 메시지 확인
- Finish 클릭하면 연결 완료

5. 확인
- 왼쪽 네비게이터에서 Schemas → Tables 클릭 → 테이블 구조 확인 가능
- 우클릭 → SQL Editor → New SQL Script 선택 후 쿼리 실행 가능
- 예:
//sql
SELECT * FROM employees;
```

---

### 🍃MongoDB 연결 방법
>전제: MongoDB 서버가 설치되어 있거나, Docker로 실행 중이어야 함
```java
1. 새 연결 만들기
- Database → New Database Connection → MongoDB 선택

2. 접속 정보 입력
- Host: localhost
- Port: 27017 (MongoDB 기본 포트, Docker에서 다르게 설정했다면 그 값)
- User/Password: MongoDB 실행 시 지정한 계정 (MONGO_INITDB_ROOT_USERNAME, MONGO_INITDB_ROOT_PASSWORD)
- 예:
//yaml
User: admin
Password: 1234

3. 드라이버 다운로드
- MongoDB JDBC 드라이버 다운로드 필요 → Download 클릭

4. 테스트 연결
- Test Connection → 성공 시 Finish

5. 확인
- 좌측 네비게이터에서 Databases → Collections 확인
- SQL Editor 대신 Mongo Shell 스타일 쿼리 사용 가능 (find 등)
- 예 (MongoDB):
//javascript
db.users.find()
```

---

## 📘 DBeaver 자주 쓰는 기능 & 단축키 정리

### SQL 편집기 관련
| 기능 | 단축키 | 설명 |
|------|--------|------|
| 자동완성 | Ctrl + Space | 테이블명, 컬럼명 자동 완성 |
| 코드 포맷팅 | Ctrl + Shift + F | SQL 문 정렬/예쁘게 배치 |
| 현재 쿼리 실행 | Ctrl + Enter | 커서 위치 SQL만 실행 |
| 전체 실행 | Alt + X <br>(또는 Ctrl + Shift + Enter) | SQL 스크립트 전체 실행 |
| 히스토리 보기 | Alt + ↑ / Alt + ↓ | 이전/다음 쿼리 불러오기 |
| 주석 처리 | Ctrl + / | 선택한 줄 주석/해제 |

### 결과창 / 데이터 조회
| 기능 | 단축키 | 설명 |
|------|--------|------|
| 데이터 새로고침 | F5 | 조회 결과 다시 불러오기 |
| 선택 영역 복사 | Ctrl + C | 결과창 데이터 복사 (CSV 형식도 가능) |
| 셀 편집 | 더블클릭 | 조회된 데이터 직접 수정 |
| 결과 내 검색 | Ctrl + F | 결과창 데이터에서 텍스트 검색 |

### 탐색기 / DB 관리
| 기능 | 단축키 | 설명 |
|------|--------|------|
| 새 연결 생성 | Ctrl + Shift + N | DB 연결 추가 |
| 연결 새로고침 | F5 | 스키마/테이블 최신화 |
| 객체 검색 | Ctrl + Shift + F | 테이블/컬럼/프로시저 이름 검색 |

### ERD / 시각화
- **자동 ERD 생성**: 스키마 → 우클릭 → ER Diagram  
- **쿼리 결과 차트 보기**: 결과창 탭에서 Grid → Charts 전환  

### 데이터 Import / Export
- **Export**: 테이블 → 우클릭 → Export Data  
  - CSV, Excel, JSON, SQL 등 지원  
- **Import**: 테이블 → 우클릭 → Import Data  
  - CSV, Excel → 테이블로 삽입 가능  

## Tip!💡
```sql
1) 쿼리 히스토리 
   - 메뉴 → Window → Database Query Manager  
   - 실행했던 쿼리 전체 확인 가능  
2) Favorite Queries (스니펫)  
   - 자주 쓰는 쿼리를 저장해두고 재사용 가능  
3) 멀티 DB 비교 
   - 같은 테이블을 다른 DB에서 열고 데이터 비교 가능  
```

---

## 📝DBeaver 주요 기능
```sql
1) DB 연결/관리
- JDBC 드라이버를 통해 다양한 DB에 접속 가능
- 여러 개의 DB를 동시에 연결하고 탭으로 전환 가능  

2) SQL 편집기
- 쿼리 작성, 실행, 결과 확인
- 자동완성, SQL 하이라이팅 지원
- 실행 계획(Execution Plan) 확인 가능 → 성능 튜닝에 도움

3) 데이터 조회/편집
- 결과를 테이블 뷰, ERD 뷰 등으로 볼 수 있음
- 조회한 데이터 직접 수정 가능 (엑셀처럼 셀 편집)

4) ERD (Entity-Relationship Diagram) 자동 생성
- DB의 테이블 구조를 불러와서 다이어그램 자동 생성
- 스키마 구조 파악이 쉬움

5) 데이터 내보내기/가져오기
- CSV, Excel, JSON, SQL 스크립트 등 다양한 포맷으로 내보내기 가능
- 외부 파일 → DB로 가져오기 가능

6) 보안/편의 기능
- 연결 암호화, SSH 터널링 지원
- 북마크, 쿼리 히스토리, 스니펫 기능 제공
```

---

## 📝DBeaver의 장점
```java
1) 올인원(All-in-one): 하나의 툴로 여러 DB 관리 가능 → 개발자/DBA가 다중 DB 환경에서 편리하게 사용

2) 무료: Community 버전만으로도 대부분의 기능 사용 가능

3) UI/UX: SQL 초보자도 쉽게 접근 가능 (엑셀처럼 테이블 수정 가능)

4) 확장성: 플러그인 설치 가능
```

---

## 📝DBeaver와 비슷한 툴
```sql
1) HeidiSQL (MySQL/MariaDB 특화, 가볍지만 DB 종류 제한적)

2) phpMyAdmin (웹 기반, MySQL 전용)

3) DataGrip (JetBrains, 유료, IDE 스타일로 고급 기능 제공)
   >> DBeaver는 무료+멀티DB 지원이라는 점에서 가장 범용성이 높음.
```

---

<a href="#top" style="display:block; text-align:right; text-decoration:none; font-size:14px;">
⬆️ 맨 위로
</a>