# SQL Developer



## 설치링크

**Link : https://www.oracle.com/database/sqldeveloper/technologies/download/**


![SQL Developer](/images/SQLDeveloperinstall.png)

>접속하면 위화면

![SQL Developer](/images/SQLDeveloperinstall_1.png)

>스크롤 내리면 현재 화면

![SQL Developer](/images/SQLDeveloperinstall_2.png)

>캡쳐된 부분 설치

![SQL Developer](/images/SQLDeveloperinstall_3.png)
>압축 풀고 위처럼 exe파일 우클릭해서 바탕화면에 바로가기 만들기(편의성)

![SQL Developer](/images/SQLDeveloperinstall_4.png)
>실행시켜보면 아직 오라클 설치 전이라 위처럼 오류나옴

![SQL Developer](/images/SQLDeveloperinstall_5.png)
>아니오 클릭시 위처럼 실행은 됨

![alt text](image-38.png)
>수동으로 접속 생성

---

## 명령어로 실행하기 `명령 프롬프트(cmd) 열고: dbca 실행`
![alt text](image-29.png)
![alt text](image-30.png)
![alt text](image-31.png)
![alt text](image-32.png)
### sys / 123456 / 123456

![alt text](image-33.png)
### test001 / test001 / test001
![alt text](image-34.png)
### 예
![alt text](image-35.png)
![alt text](image-36.png)
### 완료

## SQLDeveloper 실행 후 
좌측 상단에 oracle접속 위에 초록색 + 버튼 클릭
![alt text](image-37.png)
비밀번호 test001
이후 테이블생성할때 권한 오류 뜨면

똑같이 좌측 상단에 oracle접속 위에 초록색 + 버튼 클릭
![alt text](image-39.png)
이렇게 admin 만들어서 `grant create session, create table to test001` 이 코드 편집기에 입력해서 권한주기 이후 이전에 생성한 portal에 테이블 생성 가능





---



![alt text](image-20.png)
![alt text](image-22.png)
슈퍼어드민

**새 SQL 워크시트 : Alt + F10**


## 새 테이블 만들기
![alt text](image-40.png)
`새 테이블` 선택
![alt text](image-41.png)



## 새 뷰 만들기
![alt text](image-2.png)
`새 뷰` 선택
![alt text](image-19.png)
테스트 > 확인




## 새 인덱스 만들기
![alt text](image-26.png)
![alt text](image-24.png)












---


![alt text](image-21.png)
![alt text](image-23.png)
디비버에서 열기