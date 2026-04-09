# Run nginx Container using Docker

## 🎯 Purpose
Run an nginx web server with Docker on Windows, verify it from a browser, and understand the basic container lifecycle.

---

## 🧭 Environment
- Host OS: Windows
- Runtime: Docker Desktop
- Backend: WSL2
- Browser test URL: `http://localhost:8080`

---

## 🛠️ Main Command

```bash
docker run -d -p 8080:80 --name web1 nginx
```
🔍 Command Breakdown
docker run
Create and start a new container from an image.
If the image does not exist locally, Docker will pull it automatically from Docker Hub.

-d
Detached mode.
The container runs in the background, so the terminal is not occupied.

-p 8080:80
Port mapping.
Format:
host_port:container_port
Meaning in this case:
Host port: 8080
Container port: 80
Traffic flow:
http://localhost:8080 -> nginx inside container on port 80

--name web1
Assign a readable name to the container.
This makes it easier to manage than using a long container ID.

nginx
The image name.
Docker will use the official nginx image.

🛠️ Steps
1. Confirm Docker is running
```
docker version
docker ps
```
Expected:

Docker Engine is running
docker ps returns normally even if no containers are running
2. Run nginx container
```
docker run -d -p 8080:80 --name web1 nginx
```
Expected:

Docker returns a container ID
Container starts successfully in background
3. Verify running container
```
docker ps
```
Expected output should show:

IMAGE: nginx
NAME: web1
PORTS: 0.0.0.0:8080->80/tcp
4. Verify from browser

Open:

http://localhost:8080

Expected:

nginx default welcome page appears
🧰 Follow-up Commands
View running containers
``` docker ps ```
View all containers, including stopped ones
``` docker ps -a ```
Stop container
```docker stop web1 ```
Start container again
```docker start web1```
Remove container
```docker rm web1```

Note:

The container must be stopped before removal
🧪 Optional Verification
Check logs
```docker logs web1```
Enter container shell
```docker exec -it web1 bash```
Check nginx web directory inside container
```
cd /usr/share/nginx/html
ls
```
⚠️ Troubleshooting
Docker command works, but container does not start
Check Docker Desktop status and make sure Engine is running.
```docker version```
Browser cannot open http://localhost:8080
Check whether container is running:
```docker ps```
Check whether port mapping is correct:
```-p 8080:80```
Check whether another service is already using port 8080.
Container name already exists
Docker will reject duplicate container names.
You can remove the old container first:
```
docker stop web1
docker rm web1
```
Or use a different name.
💡 Notes
A container is a running instance of an image
An image is a reusable template
Changes made inside the container are temporary unless built into a new image or stored in volumes
Using --name is recommended for daily operations and troubleshooting
✅ Result
After this SOP is completed successfully, you should be able to:
run a container with Docker
understand the meaning of docker run -d -p 8080:80 --name web1 nginx
verify the service from a browser
stop, start, and remove the container properly
