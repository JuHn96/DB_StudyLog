# 🧩SQL Developer



## 설치링크

> 캡쳐에 관련된 설명 = 캡쳐 바로 아래 글

**Link : https://www.oracle.com/database/sqldeveloper/technologies/download/**


![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall.png)

>접속하면 위화면

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_1.png)

>스크롤 내리면 현재 화면

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_2.png)

>캡쳐된 부분 설치

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_3.png)
>압축 풀고 위처럼 exe파일 우클릭해서 바탕화면에 바로가기 만들기(편의성 관련 선택사항)

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_4.png)
>실행시켜보면 아직 오라클 설치 전이라 위처럼 오류나옴 (이 과정은 굳이 할 필요 없음 오라클 설치 이후 실행하는게 깔끔)

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_5.png)
>아니오 클릭시 위처럼 실행은 됨 (이 과정은 굳이 할 필요 없음 오라클 설치 이후 실행하는게 깔끔)

![SQL Developer](/images/SQLDeveloper/SQLDeveloperinstall_6.png)
>수동으로 접속 생성

---

## 명령어로 실행하기 `명령 프롬프트(cmd) 열고: dbca 실행`
![SQL Developer](/images/SQLDeveloper/SQLDeveloper.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_1.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_2.png)
> 칸 다 안채웠는데 칸 안의 내용 - sys / 123456 / 123456

![SQL Developer](/images/SQLDeveloper/SQLDeveloper_3.png)


![SQL Developer](/images/SQLDeveloper/SQLDeveloper_4.png)
> portal / test001 / test001 / test001

![SQL Developer](/images/SQLDeveloper/SQLDeveloper_5.png)
> 비밀번호 안전하지 않은데 계속 하겠냐는 문구 '예' 하면 진행 가능

![SQL Developer](/images/SQLDeveloper/SQLDeveloper_6.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_7.png)
> 이후 딱히 건드리는것 없이 완료

## SQLDeveloper 실행 후 
**좌측 상단에 oracle접속 위에 초록색 + 버튼 클릭**
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_8.png)
>비밀번호 test001
>이후 테이블생성할때 권한 오류 뜨면
>똑같이 좌측 상단에 oracle접속 위에 초록색 + 버튼 클릭

![SQL Developer](/images/SQLDeveloper/SQLDeveloper_9.png)
>이렇게 admin 만들어서 [`grant create session, create table to test001`] 이 코드 편집기에 입력(편집기 = 디비버에서 SQL편집기 열어서 명령어 입력하듯이 - 새 SQL 워크시트 : Alt + F10)해서 권한주기 이후 이전에 생성한 portal에 테이블 생성 가능





---



![SQL Developer](/images/SQLDeveloper/SQLDeveloper_10.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_11.png)
슈퍼어드민(제일 처음에 만들어서 테스트한 데이터베이스)

**새 SQL 워크시트 : Alt + F10**


## 새 테이블 만들기
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_12.png)
`새 테이블` 선택
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_13.png)
>위처럼 `USER_ID` / `USER_NAME` 테이블 추가 ID에 키 지정


## 새 뷰 만들기
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_14.png)
`새 뷰` 선택
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_15.png)
테스트 > 확인
> 테이블 생성 이후 해야 가능




## 새 인덱스 만들기
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_16.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_17.png)












---

## DBeaver에서 연결

![SQL Developer](/images/SQLDeveloper/SQLDeveloper_18.png)
![SQL Developer](/images/SQLDeveloper/SQLDeveloper_19.png)
디비버에서 열기(성공은 못하신것 같은데 일단 이런식으로 한다 라고 하시고 넘어감)