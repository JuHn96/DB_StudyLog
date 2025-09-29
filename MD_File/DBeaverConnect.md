DBeaver에서 로컬 MariaDB(3308) 연결

DBeaver 실행 → 좌측 상단 “New Connection(+)” 클릭

목록에서 MariaDB 선택 → Next

만약 MariaDB가 안 보이면 MySQL이랑 거의 동일하게도 연결 가능하지만, MariaDB 드라이버가 있으면 그걸 쓰세요.

Connection 설정값

Host: 127.0.0.1

Port: 3308 ← 설치 시 지정한 값

Database: 비워두거나, 생성해둔 DB명(예: testdb)

Username: root

Password: (설치 때 만든 비밀번호)

Save password: 체크(선택)

“Test Connection” 클릭

“Driver files missing” 팝업이 나오면 Download 눌러 드라이버 받기

성공 메시지 확인 후 Finish

접속 후 상단 SQL Editor 열고 아래로 빠르게 동작 확인:

SHOW DATABASES;
CREATE DATABASE IF NOT EXISTS testdb;
USE testdb;

CREATE TABLE IF NOT EXISTS users (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  email VARCHAR(100)
);

INSERT INTO users (name, email) VALUES ('주환님', 'test@example.com');
SELECT * FROM users;

연결이 안 될 때 빠른 체크

서비스: services.msc → MariaDB가 실행 중인지 확인

포트: my.ini의 port=3308 확인(기본 경로: C:\Program Files\MariaDB 11.4\data\my.ini 근처)

포트 충돌: netstat -ano | findstr 3308 (다른 프로세스가 점거 X)