# Modify nginx Content inside Docker Container

## 🎯 Purpose
Modify nginx default page inside a running container.

---

## 🛠️ Steps

### 1. Enter container

docker exec -it web1 bash

2. Navigate to web directory
```
cd /usr/share/nginx/html.
```
4. Modify index.html
```
echo "<h1>Hello DevOps</h1>" > index.html
```
6. Verify in browser
http://localhost:8080
