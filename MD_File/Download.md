<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>

# 📥Download Page

---

## 🐿️DBeaver
**Link : https://dbeaver.io/download/**  

![dbeaver](/images/dbeaver.png)  
>링크에 들어가서 위 사진처럼 `installer`로 되어있는것 클릭해서 설치



![dbeaver](/images/dbeaverinstall.png)  
**이후 위 화면이 나오면 개인 PC기준 `아래[For me(JuHn)]` 추천**  
>위는 PC 안에 있는 모든 계정(사용자)에서 DBeaver를 사용할 수 있도록 설치(관리자 권한 필요할 수 있음)

![alt text](/images/dbeaverinstall_2.png)  


**넘어가면 위 화면이 나오는데 그대로 다음**  
```java
* 체크박스 설명
- DBeaver Community: 본체 프로그램 (필수)
- Include Java: DBeaver 실행에 필요한 Java Runtime 포함 (보통 체크 권장, 따로 JDK/JRE 안 깔아도 됨)
- Reset Settings: 이전에 설치한 설정(테마, 연결 정보 등)을 초기화할 때 사용(새로 설치라면 필요 없음)
- Associate SQL files: .sql 파일을 더블클릭하면 DBeaver에서 열리도록 연결
- Associate SQLite database files: .sqlite 파일을 더블클릭하면 DBeaver에서 열리도록 연결
```

![alt text](/images/dbeaverinstall_3.png)  
**설치 경로 설정 화면`현재 집에서 DB폴더로 DB관련된 소프트웨어 모아서 관리하기 위해 위처럼 경로설정`**  

![alt text](/images/dbeaverinstall_4.png)

시작메뉴에 바로가기 만들것인지 선택하는 화면(깔끔하게 하기위해 `DBeaver Community > DBeaver`로 변경)

>이후 마지막 화면에 Create Desktop Shortcut 이라는 체크박스는 바탕화면 바로가기 만들것인지 여부

---

## 🐳Docker

**Link : https://www.docker.com/products/docker-desktop**
- Windows 10 Pro 이상 → Hyper-V / Home → WSL2 필요  
- 설치 후 재부팅 → 작업표시줄에 🐳 아이콘 확인  


## 설치 확인 및 실행

**설치 확인**
```sql
docker --version
예시: Docker version 27.0.3, build a878d
```
**테스트 실행**
```sql
docker run hello-world
```
"Hello from Docker!" 나오면 정상 설치 완료

**MySQL 실행 예시**
```sql
docker run -d --name mysql8-container `
  -e MYSQL_ROOT_PASSWORD=1234 `
  -p 3307:3306 `
  mysql:8.0
```
**실행 확인**
```sql
docker ps
docker exec -it mysql8-container mysql -u root -p
>>(root 비번: 1234)
```

---




<a href="#top" style="display:block; text-align:right; text-decoration:none; font-size:14px;">
⬆️ 맨 위로
</a>