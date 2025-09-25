<a href="../ReadMe.md" style="float:right;">🏠Home</a><a id="top"></a>

# 🐳Docker Run Code List

---

### 🐘PostgreSQL
```
docker run -d `
  --name postgres-container `
  -e POSTGRES_USER=testuser `
  -e POSTGRES_PASSWORD=testpw `
  -e POSTGRES_DB=test123 `
  -p 5432:5432 `
  -v pgdata:/var/lib/postgresql/data `
  postgres:15
```

### 🍃MongoDB
```
docker run -d `
  --name mongodb `
  -e MONGO_INITDB_ROOT_USERNAME=admin `
  -e MONGO_INITDB_ROOT_PASSWORD=1234 `
  -p 27017:27017 `
  mongo:latest
```

### 🐬MySQL
```
docker run -d `
  --name mysql8-container `
  -e MYSQL_ROOT_PASSWORD=1234 `
  -e MYSQL_DATABASE=testdb `
  -e MYSQL_USER=testuser `
  -e MYSQL_PASSWORD=testpw `
  -p 3307:3306 `
  -v mysql_data:/var/lib/mysql `
  mysql:8.0.4
```

---









<a href="#top" style="display:block; text-align:right; text-decoration:none; font-size:14px;">⬆️ 맨 위로</a>