# Docker nginx Reverse Proxy Basics

## 🎯 Purpose
Use nginx as a reverse proxy in front of a backend application container.

---

## 🧭 Architecture

```text
Browser -> localhost:8080 -> nginx -> app:8000
```
📁 Project Structure
reverse-proxy-demo/
├── compose.yaml
├── app/
│   ├── Dockerfile
│   └── server.py
└── nginx/
    └── default.conf
🛠️ Backend App
app/server.py
```
from http.server import BaseHTTPRequestHandler, HTTPServer

class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type", "text/plain; charset=utf-8")
        self.end_headers()
        self.wfile.write(b"Hello from backend app via nginx reverse proxy")

server = HTTPServer(("0.0.0.0", 8000), Handler)
print("Backend app listening on port 8000")
server.serve_forever()
```
app/Dockerfile
```
FROM python:3.12-slim
WORKDIR /app
COPY server.py /app/server.py
EXPOSE 8000
CMD ["python", "server.py"]
```
🛠️ nginx Config
nginx/default.conf
```
server {
    listen 80;
    server_name localhost;

    location / {
        proxy_pass http://app:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```
🛠️ compose.yaml
```
services:
  app:
    build: ./app
    container_name: app1

  web:
    image: nginx
    container_name: web1
    ports:
      - "8080:80"
    volumes:
      - ./nginx/default.conf:/etc/nginx/conf.d/default.conf
    depends_on:
      - app
```
🛠️ Steps
1. Build and start services
```docker compose up -d --build```
2. Verify services
```docker compose ps```
3. Test in browser
```http://localhost:8080```
4. View logs
5.
```
docker compose logs
docker compose logs web
docker compose logs app
```
6. Stop services
```docker compose down```
💡 Key Concepts
nginx works as a reverse proxy
app service does not need host port exposure
service name app can be used directly in proxy_pass
this is the foundation of a two-tier container architecture
