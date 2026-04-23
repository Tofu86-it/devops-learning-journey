# Docker Compose Environment Variables Basics

## 🎯 Purpose
Use environment variables in Docker Compose to configure backend application behavior.

---

## 🧭 Concept

Environment variables allow application settings to be configured without changing source code.

---

## 🛠️ Example Python App

```python
import os
from http.server import BaseHTTPRequestHandler, HTTPServer

APP_NAME = os.getenv("APP_NAME", "Default App")
APP_ENV = os.getenv("APP_ENV", "dev")
APP_MESSAGE = os.getenv("APP_MESSAGE", "Hello from backend app")

class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type", "text/plain; charset=utf-8")
        self.end_headers()

        response = (
            f"App Name: {APP_NAME}\n"
            f"Environment: {APP_ENV}\n"
            f"Message: {APP_MESSAGE}\n"
        )
        self.wfile.write(response.encode("utf-8"))

server = HTTPServer(("0.0.0.0", 8000), Handler)
print(f"Backend app listening on port 8000 | APP_NAME={APP_NAME} | APP_ENV={APP_ENV}")
server.serve_forever()
```
🛠️ compose.yaml Example
```services:
  app:
    build: ./app
    container_name: app1
    environment:
      APP_NAME: DevOps Lab
      APP_ENV: Learning
      APP_MESSAGE: Hello from backend app via nginx reverse proxy

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
1. Update application code to read environment variables
2. Add environment section in compose.yaml
3. Rebuild and restart services
```
docker compose down
docker compose up -d --build
```
4. Verify in browser
http://localhost:8080
5. Check logs
```docker compose logs app```

💡 Key Concepts

1.Environment variables separate configuration from source code

2.Docker Compose can inject settings into containers

3.The same app image can behave differently in different environments
