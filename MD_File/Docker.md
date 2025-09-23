🐳 Docker란?

정의:
애플리케이션과 그 실행 환경(라이브러리, 의존성, OS 환경 등)을 컨테이너(container) 라는 독립된 단위로 묶어 실행할 수 있게 해주는 플랫폼.

비유:
프로그램을 직접 PC에 설치하면 환경(윈도우/리눅스 차이, 버전 충돌 등) 때문에 문제가 생기기 쉬움 →
Docker는 “표준화된 박스(컨테이너)” 안에 애플리케이션 + 필요한 환경을 넣어 두고, 어디서든 똑같이 실행되도록 해줌.

📦 핵심 개념
개념	설명
이미지(Image)	실행 파일, 라이브러리, 설정값 등을 묶어 둔 “컨테이너 설계도”. (예: mysql:8.0, node:18)
컨테이너(Container)	이미지를 실제로 실행한 인스턴스. 하나의 이미지로 여러 개 컨테이너 실행 가능.
Docker Hub	공개된 이미지 저장소. (GitHub의 Docker 버전 느낌)
Dockerfile	이미지 빌드(만들기) 규칙을 적은 파일. (예: FROM node:18 → Node.js 18 버전 기반으로 이미지 생성)
⚙️ 장점

환경 일관성: 내 PC, 서버, 클라우드 어디서 실행해도 동일하게 동작.

빠른 배포: 실행 환경 통째로 패키징 → 바로 실행 가능 (docker run ...).

격리성: 컨테이너끼리 독립적으로 동작, 충돌 없음.

확장성: 필요하면 컨테이너 여러 개 띄워서 부하 분산 가능.

🖥️ 기본 명령어
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

🚀 예시 시나리오

✅ MySQL을 설치하려고 할 때:

보통은 직접 설치하면 OS 맞춰서 설치파일 내려받고, 환경변수 잡고, 충돌 문제 해결해야 함.

Docker에서는:

docker run -d --name mysql8-container \
  -e MYSQL_ROOT_PASSWORD=1234 \
  -e MYSQL_DATABASE=testdb \
  -p 3307:3306 \
  mysql:8.0


→ 몇 초 만에 DB 서버 실행 완료.

📝 요약

Docker = “어디서나 똑같이 실행되는 표준화된 실행 환경”

이미지 → 컨테이너 구조

개발/운영 환경 차이 줄이고, 배포 및 관리 효율 극대화

---

🐳 1. Docker 개념 정리 (빠른 복습)

Docker = 어디서든 동일하게 실행되는 실행 환경 제공 플랫폼

이미지(Image): 실행 설계도

컨테이너(Container): 이미지를 실행한 인스턴스

Docker Hub: 이미지 저장소

Dockerfile: 이미지 빌드 규칙

➡️ 한마디로 “개발 환경을 담은 박스를 만들어, 누구나 똑같이 실행할 수 있게 해주는 도구”

💾 2. Docker 설치 & 다운로드 과정
🖥️ Windows 설치

Docker Desktop 다운로드

공식 홈페이지: https://www.docker.com/products/docker-desktop

Windows(특히 Windows 10/11) → Docker Desktop 설치

필요 조건

Windows 10 Pro 이상 → Hyper-V 지원됨

Windows 10 Home → WSL2(리눅스 서브시스템) 필요

설치 후 확인

docker --version


예:

Docker version 27.0.3, build 12345

🐧 Linux 설치 (예: Ubuntu)
# 기존 패키지 업데이트
sudo apt update
sudo apt upgrade -y

# docker 설치
sudo apt install -y docker.io

# 서비스 시작 및 부팅 시 자동 실행
sudo systemctl start docker
sudo systemctl enable docker

# 버전 확인
docker --version

🍏 macOS 설치

Docker Desktop for Mac 다운로드 → https://www.docker.com/products/docker-desktop

설치 후 터미널에서 확인:

docker --version

⚙️ 3. 기본 실습 (다운로드 + 실행)
① 이미지 다운로드
docker pull hello-world


테스트용 초간단 이미지 (정상 동작 확인용)

② 컨테이너 실행
docker run hello-world


"Hello from Docker!" 메시지가 나오면 성공 ✅

③ MySQL 실행 예시
docker run -d --name mysql8-container \
  -e MYSQL_ROOT_PASSWORD=1234 \
  -e MYSQL_DATABASE=testdb \
  -e MYSQL_USER=testuser \
  -e MYSQL_PASSWORD=testpw \
  -p 3307:3306 \
  mysql:8.0


-d → 백그라운드 실행

-p 3307:3306 → 로컬 3307 포트를 컨테이너 3306 포트와 연결

환경 변수로 DB 초기 세팅

④ 실행 확인
docker ps


→ 실행 중인 컨테이너 목록 출력

📌 요약

Docker 설치 (Docker Desktop or apt install)

docker pull hello-world → 정상 동작 확인

docker run mysql:8.0 ... → 실제 DB 띄워보기

---

🐳 Windows에서 Docker 설치 & 사용하기
1️⃣ 설치 전 준비

Windows 10/11 Pro/Enterprise → Hyper-V 가상화 지원됨.

Windows 10 Home → WSL2(Windows Subsystem for Linux) 필요.

👉 본인 PC에서 WSL2 + 가상화(Virtualization) 가 켜져 있어야 함. (BIOS에서 Intel VT-x / AMD-V 옵션 ON 확인)

2️⃣ Docker Desktop 설치

공식 다운로드 페이지 접속:
👉 Docker Desktop for Windows

설치 파일 실행 후 → 기본 옵션으로 설치 진행.

설치 완료 후 재부팅.

작업 표시줄에서 Docker Desktop 실행 → 고래 아이콘 🐳 뜨면 정상 동작.

3️⃣ 설치 확인

Windows PowerShell(또는 CMD) 열고 입력:

docker --version


예시 출력:

Docker version 27.0.3, build a878d

4️⃣ 첫 실행 테스트
docker run hello-world


✅ 출력 예시:

Hello from Docker!
This message shows that your installation appears to be working correctly.

5️⃣ MySQL 컨테이너 실행 예시
docker run -d --name mysql8-container `
  -e MYSQL_ROOT_PASSWORD=1234 `
  -e MYSQL_DATABASE=testdb `
  -e MYSQL_USER=testuser `
  -e MYSQL_PASSWORD=testpw `
  -p 3307:3306 `
  mysql:8.0


-d → 백그라운드 실행

--name → 컨테이너 이름(mysql8-container)

-p → 포트 매핑 (내PC 3307 → 컨테이너 3306)

-e → 환경변수(DB 초기 설정)

6️⃣ 실행 확인
docker ps


실행 중인 컨테이너 목록 출력.

docker logs mysql8-container


컨테이너 로그 확인.

docker exec -it mysql8-container mysql -u root -p


컨테이너 안에서 MySQL 접속 (비번은 위에서 1234).

✅ 정리

Docker Desktop 설치 → PowerShell에서 docker run hello-world 로 정상 확인.

MySQL 같은 DB를 띄울 때도 설치가 아니라 docker run 명령어 한 줄로 실행 가능.

---

🐳 Windows Docker 실습 — MySQL + MongoDB
1️⃣ Docker 설치 확인

PowerShell 열고:

docker --version


출력 예시:

Docker version 27.0.3, build a878d

2️⃣ Hello World 테스트
docker run hello-world


👉 "Hello from Docker!" 나오면 정상 설치 완료 ✅

3️⃣ MySQL 컨테이너 실행
docker run -d --name mysql8-container `
  -e MYSQL_ROOT_PASSWORD=1234 `
  -e MYSQL_DATABASE=testdb `
  -e MYSQL_USER=testuser `
  -e MYSQL_PASSWORD=testpw `
  -p 3307:3306 `
  mysql:8.0


-e MYSQL_ROOT_PASSWORD=1234 → root 비밀번호 지정

-e MYSQL_DATABASE=testdb → testdb 라는 DB 자동 생성

-p 3307:3306 → 내 PC(3307) ↔ 컨테이너(3306) 연결

👉 확인:

docker ps
docker exec -it mysql8-container mysql -u root -p


(root 비밀번호 = 1234)

4️⃣ MongoDB 컨테이너 실행
docker run -d --name mongodb-container `
  -e MONGO_INITDB_ROOT_USERNAME=admin `
  -e MONGO_INITDB_ROOT_PASSWORD=1234 `
  -p 27017:27017 `
  mongo:latest


-e MONGO_INITDB_ROOT_USERNAME=admin → 관리자 계정

-e MONGO_INITDB_ROOT_PASSWORD=1234 → 관리자 비밀번호

-p 27017:27017 → MongoDB 기본 포트 매핑

👉 확인:

docker ps
docker logs mongodb-container

5️⃣ MongoDB 접속 방법

컨테이너 내부에서 접속:

docker exec -it mongodb-container mongosh -u admin -p 1234


→ test> 프롬프트가 나오면 정상 접속.

GUI 클라이언트 (예: DBeaver, MongoDB Compass)에서도 접속 가능:

mongodb://admin:1234@localhost:27017

6️⃣ 실행 중인 컨테이너 확인
docker ps


예시 출력:

CONTAINER ID   IMAGE        PORTS                     NAMES
a1b2c3d4e5f6   mysql:8.0    0.0.0.0:3307->3306/tcp    mysql8-container
f6e5d4c3b2a1   mongo        0.0.0.0:27017->27017/tcp  mongodb-container

✅ 정리

MySQL → docker run ... mysql:8.0

MongoDB → docker run ... mongo:latest

둘 다 컨테이너로 실행하므로, 설치 없이 바로 DB 서버 구동 가능.

DBeaver 같은 툴에서 MySQL, MongoDB 동시에 접속 관리 가능.