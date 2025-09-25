<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>

# 🐳Docker - [📥](Download.md)

[📜DockerRunCodeList](/MD_File/DockerRunCd.md)

---

### Docker란?

**정의:** 애플리케이션과 그 실행 환경(라이브러리, 의존성, OS 환경 등)을 컨테이너`container` 라는 독립된 단위로 묶어 실행할 수 있게 해주는 플랫폼.

**비유:** 프로그램을 직접 PC에 설치하면 환경(윈도우/리눅스 차이, 버전 충돌 등) 때문에 문제가 생기기 쉬움 → `Docker`는 “표준화된 박스(컨테이너)” 안에 애플리케이션 + 필요한 환경을 넣어 두고, 어디서든 똑같이 실행되도록 해줌.

---

## 📦 핵심 개념

### 개념	설명
**이미지(Image):**	실행 파일, 라이브러리, 설정값 등을 묶어 둔 “컨테이너 설계도”. (예: mysql:8.0, node:18)
**컨테이너(Container):**	이미지를 실제로 실행한 인스턴스. 하나의 이미지로 여러 개 컨테이너 실행 가능.
**Docker Hub:**	공개된 이미지 저장소. (GitHub의 Docker 버전 느낌)
**Dockerfile:**	이미지 빌드(만들기) 규칙을 적은 파일. (예: FROM node:18 → Node.js 18 버전 기반으로 이미지 생성)


### ⚙️ 장점
**환경 일관성:** 내 PC, 서버, 클라우드 어디서 실행해도 동일하게 동작.
**빠른 배포:** 실행 환경 통째로 패키징 → 바로 실행 가능 (docker run ...).
**격리성:** 컨테이너끼리 독립적으로 동작, 충돌 없음.
**확장성:** 필요하면 컨테이너 여러 개 띄워서 부하 분산 가능.

---

### 🖥️ 기본 명령어
```sql
# 이미지 다운로드
docker pull mysql:8.0

# 컨테이너 실행 (백그라운드)
docker run -d --name my-mysql -e MYSQL_ROOT_PASSWORD=1234 -p 3306:3306 mysql:8.0

# 실행 중인 컨테이너 확인
docker ps

# 컨테이너 접속
docker exec -it my-mysql bash

# 컨테이너 중지/삭제
docker stop my-mysql
docker rm my-mysql
```

---

### 🐳Docker 개념 정리(요약)

**Docker:** 어디서든 동일하게 실행되는 실행 환경 제공 플랫폼

**이미지(Image):** 실행 설계도

**컨테이너(Container):** 이미지를 실행한 인스턴스

**Docker Hub:** 이미지 저장소

**Dockerfile:** 이미지 빌드 규칙

>한마디로 “개발 환경을 담은 박스를 만들어, 누구나 똑같이 실행할 수 있게 해주는 도구”

---

### ⚙️기본 실습 (다운로드 + 실행)

**이미지 다운로드**
```sql
docker pull hello-world
```
**`테스트용 초간단 이미지 (정상 동작 확인용)`**

**컨테이너 실행**
```sql
docker run hello-world
```
`"Hello from Docker!" 메시지가 나오면 성공 ✅`

**MySQL 실행 예시**
```sql
docker run -d --name mysql8-container \
  -e MYSQL_ROOT_PASSWORD=1234 \    //root 비밀번호 지정
  -e MYSQL_DATABASE=testdb \       //testdb 라는 DB 자동 생성
  -e MYSQL_USER=testuser \
  -e MYSQL_PASSWORD=testpw \
  -p 3307:3306 \                   //내 PC(3307) ↔ 컨테이너(3306) 연결
  mysql:8.0
```
- `-d` → 백그라운드 실행

- `--name` → 컨테이너 이름(mysql8-container)

- `-p` → 포트 매핑 (내PC 3307 → 컨테이너 3306)

- `-e` → 환경변수(DB 초기 설정)

**실행 확인**
- **실행 중인 컨테이너 목록 출력**
```sql
docker ps
```
*예시 출력:
```sql
CONTAINER ID   IMAGE        PORTS                     NAMES
a1b2c3d4e5f6   mysql:8.0    0.0.0.0:3307->3306/tcp    mysql8-container
f6e5d4c3b2a1   mongo        0.0.0.0:27017->27017/tcp  mongodb-container
```
- **컨테이너 로그 확인**
```sql
docker logs mysql8-container
```
- **테이너 안에서 MySQL 접속 (비번은 위에서 1234)**
```sql
docker exec -it mysql8-container mysql -u root -p
```

---

**📝 요약**

1. **Docker** = “어디서나 똑같이 실행되는 표준화된 실행 환경”
2. 이미지 → 컨테이너 구조
3. 개발/운영 환경 차이 줄이고, 배포 및 관리 효율 극대화
4. Docker 설치 (Docker Desktop or apt install)
5. `docker pull hello-world` → 정상 동작 확인
6. `docker run mysql:8.0 ...` → 실제 DB 띄워보기
7. 정리
```sql
MySQL → docker run ... mysql:8.0
MongoDB → docker run ... mongo:latest
둘 다 컨테이너로 실행하므로, 설치 없이 바로 DB 서버 구동 가능.
DBeaver 같은 툴에서 MySQL, MongoDB 동시에 접속 관리 가능.
```
---

<a href="#top" style="display:block; text-align:right; text-decoration:none; font-size:14px;">
⬆️ 맨 위로
</a>