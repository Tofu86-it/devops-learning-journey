# Docker Compose Multi-Service Basics

## 🎯 Purpose
Understand how Docker Compose manages multiple services in one project.

---

## 🧭 Example Structure

```yaml
services:
  web:
    image: nginx
    container_name: web1
    ports:
      - "8080:80"

  app:
    image: httpd
    container_name: app1
    ports:
      - "8081:80"
```
🛠️ Steps
1. Start services
```docker compose -f .\compose-multi.yaml up -d```
2. Check status
```docker compose -f .\compose-multi.yaml ps```
3. View logs
```docker compose -f .\compose-multi.yaml logs web```
```docker compose -f .\compose-multi.yaml logs app```
4. Test from browser
http://localhost:8080
http://localhost:8081
5. Stop services
```docker compose -f .\compose-multi.yaml down```

💡 Key Concepts
A compose file can manage multiple services
Each service usually maps to one container
Services run in the same compose project network
Compose describes the whole system, not just one container
