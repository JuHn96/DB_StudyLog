# Oracle  
**express edition**

---

## 설치링크  
**Link : https://www.oracle.com/database/technologies/appdev/xe.html**

![Oracle](/images/Oracleinstall_2.png)
>링크 접속하면 위 화면

![Oracle](/images/Oracleinstall.png)
>위 버튼 클릭

![Oracle](/images/Oracleinstall_3.png)
>위 화면으로 이동

![Oracle](/images/Oracleinstall_4.png)
>위 버튼 클릭

![Oracle](/images/Oracleinstall_5.png)
>설치후 압축풀면 위 화면에서 setup.exe 실행

![Oracle](/images/Oracleinstall_6.png)
> 다음

![Oracle](/images/Oracleinstall_7.png)
> 동의함

![Oracle](/images/Oracleinstall_8.png)
> 경로 설정( 사님은 c 에 oracle21xe 폴더 만들어서 설치 )이후 다음

![Oracle](/images/Oracleinstall_9.png)
> 비밀번호 123456으로 설정하셔서 그대로 함.(본인선택) 이후 다음

![Oracle](/images/Oracleinstall_10.png)
> 설치 안내문 설치

![alt text](image.png)
> 설치 성공

---
## 오류
![Oracle](image-6.png)
>위 오류떴을시

![Oracle](image-18.png)
>서비스 창 실행 서비스에서 OracleServiceXE, OracleServiceORCL 같은 게 있으면 중지 & 삭제

>이후 기존 설치폴더 삭제

>환경 변수 PATH 안에 Oracle 관련 경로 있으면 삭제

>이후 setup.exe 관리자 권한으로 실행

> 설치 경로를 기본(C:\OracleXE) 그대로 두는 게 안전

---
## 정보

![Oracle](/images/Oracle.png)
이 경로 안에 실제 데이터




---


### 설치하는동안 해본다고 설치함(ㅇㅅㅁ이 건의해서) 결론 중도포기 안함 도커관련

![Oracle](image-7.png)

![Oracle](image-8.png)
설치하면 아래 화면으로 이동
![Oracle](image-9.png)
위에 확장 설치하고 Docker 실행
![Oracle](image-10.png)
이후 검색
![Oracle](image-11.png)
상단 페이지로 이동
![Oracle](image-13.png)
![Oracle](image-14.png)
copy해서 복사
![Oracle](image-15.png)
위처럼 PowerShell에서 복사한것 붙여넣고 실행
![Oracle](image-17.png)
그럼 위 처럼 설치함

1단계: Docker Desktop 준비

Docker Desktop 실행 (작업표시줄 고래 아이콘 확인).

PowerShell이나 CMD에서 정상 동작 확인:

docker version

2단계: Oracle Container Registry 로그인

Oracle 공식 이미지를 받으려면 로그인 절차가 필요합니다.

docker login container-registry.oracle.com


Oracle 계정(무료 Oracle 계정)을 입력해야 합니다.

3단계: Oracle Database 이미지 받기
docker pull container-registry.oracle.com/database/enterprise:19.3.0.0


→ 이 명령으로 Oracle Database 19c Enterprise Edition 이미지를 로컬에 다운로드합니다.

4단계: 컨테이너 실행

이제 캡처에 나온 명령을 입력합니다:

docker run -d `
  --name oracle-db `
  -p 11521:1521 `
  -p 5500:5500 `
  -e ORACLE_SID=ORCLCDB `
  -e ORACLE_PDB=ORCLPDB1 `
  -e ORACLE_PWD=MyPassw0rd `
  container-registry.oracle.com/database/enterprise:19.3.0.0


--name oracle-db → 컨테이너 이름

-p 11521:1521 → 호스트 11521 ↔ 컨테이너 1521 (DB 포트)

-p 5500:5500 → 웹 관리 포트 (Enterprise Manager Express)

-e 옵션 → DB 초기 환경 변수 설정

마지막 줄 → 사용할 이미지

5단계: 컨테이너 상태 확인
docker ps


→ oracle-db 컨테이너가 떠 있어야 합니다.

로그 확인:

docker logs -f oracle-db


→ DATABASE IS READY TO USE! 메시지가 나오면 DB 준비 완료.

6단계: 접속 테스트

SQL Developer에서:

호스트: localhost

포트: 11521

SID: ORCLCDB

PDB: ORCLPDB1

사용자: system 또는 sys as sysdba

비밀번호: MyPassw0rd

👉 요약:

Docker 실행

docker login container-registry.oracle.com

docker pull ...

docker run ... (환경변수 포함)

docker ps, docker logs 확인

SQL Developer에서 접속

이 작업 하신것 같음 도커에 올리고 실행하는 작업

---
