# Build Custom nginx Image with Dockerfile

## 🎯 Purpose
Build a custom nginx image with a customized index page.

---

## 🧭 Files
- Dockerfile
- index.html

---

## 🛠️ Steps

### 1. Create index.html

```html
<h1>Hello DevOps from Dockerfile</h1>
```
2. Create Dockerfile
FROM nginx
COPY index.html /usr/share/nginx/html/index.html
3. Build image
```
docker build -t my-nginx:v1 .
```
5. Verify image
```
docker images
```
6. Run container
```
docker run -d -p 8080:80 --name web1 my-nginx:v1
```
7. Verify in browser
http://localhost:8080
