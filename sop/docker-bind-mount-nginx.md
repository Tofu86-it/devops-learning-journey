# Run nginx with Bind Mount using Docker Compose

## 🎯 Purpose
Use bind mount to store website content on the host machine and serve it through nginx container.

---

## 🧭 Environment
- Host OS: Windows
- Runtime: Docker Desktop
- Backend: WSL2

---

## 📁 Project Structure

```text
nginx-demo/
├── compose.yaml
└── html/
    └── index.html
```
🛠️ compose.yaml
```
services:
  web:
    image: nginx
    container_name: web1
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
```
🛠️ Steps
1. Create html folder
html/
2. Create index.html
```
<h1>Hello DevOps from Bind Mount</h1>
<p>Day 5 - Docker data persistence practice</p>
```
3. Start service
```
docker compose down
docker compose up -d
```
5. Verify service
```docker compose ps```
6. Verify in browser
http://localhost:8080
7. Modify host file
Edit:
html/index.html
add v2 or somthing.
Then refresh the browser.
