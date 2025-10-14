명령어 | 설명 | 예시 |
|--------|------|------|
| **SELECT** | 데이터 조회 | `SELECT * FROM product;` |
| **INSERT** | 데이터 추가 | `INSERT INTO product VALUES (1, '노트북', 1200000);` |
| **UPDATE** | 데이터 수정 | `UPDATE product SET price = 1150000 WHERE id = 1;` |
| **DELETE** | 데이터 삭제 | `DELETE FROM product WHERE id = 1;` |
| **MERGE** | 조건에 따라 INSERT 또는 UPDATE 수행 (Oracle 등) | `MERGE INTO target USING source ON (...) WHEN MATCHED THEN UPDATE ...;` |x`




| 구분 | 다루는 대상 | 자동 커밋 | 주요 명령어 | 사용 목적 |
|------|---------------|------------|--------------|--------------|
| **DDL** | 구조 (테이블, 뷰, 인덱스 등) | :흰색_확인_표시: 예 | `CREATE`, `ALTER`, `DROP`, `TRUNCATE`, `RENAME` | DB 스키마 정의 |
| **DML** | 데이터 (행/열 내용) | :x: 아니요 | `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `MERGE` | CRUD 조작 |
| **DCL** | 권한 / 보안 | :흰색_확인_표시: 예 | `GRANT`, `REVOKE`, `DENY` | 사용자 접근 제어 |
| **TCL** | 트랜잭션 | :x: 아니요 | `COMMIT`, `ROLLBACK`, `SAVEPOINT`, `SET TRANSACTION` | 데이터 변경 관리 |