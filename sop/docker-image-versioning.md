# Docker Image Versioning Basics

## 🎯 Purpose
Build and manage multiple versions of a custom Docker image.

---

## 🛠️ Steps
### 1. Update application content
Edit `index.html`:

```html
<h1>Hello DevOps from Dockerfile v2</h1>
```
2. Build new image version
```docker build -t my-nginx:v2 .```
3. Verify images
```docker images```
4. Stop and remove old container
```
docker stop web1
docker rm web1
```
5. Run new version
```docker run -d -p 8080:80 --name web1 my-nginx:v2```
6. Verify in browser
http://localhost:8080
