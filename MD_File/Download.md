<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>

# 📥Download Page

---

## 🐿️DBeaver
**Link : https://dbeaver.io/download/**  
>링크에 들어가서 아래 사진처럼 `installer`로 되어있는것 클릭해서 설치

![dbeaver](/images/dbeaver.png)  

---

## 🐳Docker
### Docker 설치 & 확인 (Windows)

## 설치 링크
**Link : https://www.docker.com/products/docker-desktop**
- Windows 10 Pro 이상 → Hyper-V / Home → WSL2 필요  
- 설치 후 재부팅 → 작업표시줄에 🐳 아이콘 확인  

---

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