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



---
![alt text](image-38.png)
수동으로 접속 생성







![alt text](image-20.png)
![alt text](image-22.png)
슈퍼어드민

**새 SQL 워크시트 : Alt + F10**





![alt text](image-21.png)
![alt text](image-23.png)
디비버에서 열기






![alt text](image-25.png)
??? [비밀번호 규제 강력 `대문자``소문자``숫자``특문`]비밀번호/비밀번호 확인 - 
>중도포기 - 사유 : 메모리부족


![alt text](image-1.png)

첫줄
```
insert into users values('a001', '한글')
```

![alt text](image-2.png)
`새 뷰` 선택
![alt text](image-3.png)
테스트 > 확인


![alt text](image-4.png)



![alt text](image-5.png)
![alt text](image-19.png)




![alt text](image-26.png)
![alt text](image-24.png)


명령어로 실행하기
명령 프롬프트(cmd) 열고:

dbca
![alt text](image-27.png)
![alt text](image-28.png)













![alt text](image-29.png)
![alt text](image-30.png)
![alt text](image-31.png)
![alt text](image-32.png)
sys / 123456 / 123456
![alt text](image-33.png)
test001 / test001 / test001
![alt text](image-34.png)
예
![alt text](image-35.png)
![alt text](image-36.png)
완료

![alt text](image-37.png)
비밀번호 test001




![alt text](image-39.png)
admin 만들어서
grant create session, create table to test001 이거 입력해서 권한주기 이후 portal 테이블 생성 가능

