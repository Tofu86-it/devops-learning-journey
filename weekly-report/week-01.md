# Week 01 - DevOps Journey Start with Docker

## This Week's Focus

- Set up learning management and portfolio structure
- Create GitHub repository for DevOps learning
- Install Docker Desktop on Windows
- Understand WSL2 backend and Docker storage behavior
- Run and manage nginx container
- Start building a custom nginx image with Dockerfile

## Completed Tasks

- Created GitHub repository: `devops-learning-journey`
- Added initial `README.md`
- Created weekly report structure
- Created SOP documents for EC2/nginx and Docker-related tasks
- Installed Docker Desktop with WSL2 backend
- Adjusted Docker storage location to D drive
- Verified Docker Engine is running normally
- Tested Docker CLI with `docker version` and `docker ps`
- Ran nginx container with:
  `docker run -d -p 8080:80 --name web1 nginx`
- Renamed and managed container using container name
- Entered container using `docker exec -it web1 bash`
- Modified nginx default page inside the container
- Verified modified page from browser
- Created custom nginx project files:
  - `project/nginx-demo/Dockerfile`
  - `project/nginx-demo/index.html`
- Learned how `docker build -t my-nginx:v1 .` works

## What I Learned

- Docker Desktop on Windows runs through WSL2
- Docker data is stored in a virtual disk (VHDX), not as normal folders
- Image is a template, container is a running instance
- `docker run` creates and starts a new container
- `-d` means detached mode (run in background)
- `-p 8080:80` maps host port 8080 to container port 80
- `--name web1` makes container management easier
- Changes made inside a container are temporary
- Dockerfile is the correct way to make deployment repeatable

## Problems Encountered

- AWS account verification could not proceed due to SMS issue
- Docker Engine failed to start during initial setup
- WSL memory/CPU allocation was too low
- Uncertainty about Docker storage location
- Confusion about why VHDX still exists after deleting a container
- Needed to understand Docker command parameters in detail

## Solutions

- Switched temporarily from AWS learning path to local Docker practice
- Increased WSL resources and confirmed Docker Engine startup
- Moved Docker storage to D drive
- Learned that `docker rm` removes containers only, not the VHDX file itself
- Clarified Docker command usage and container lifecycle
- Used named containers instead of random container IDs for easier operations

## Repository Outputs This Week

- `README.md`
- `weekly-report/week-01.md`
- `project/nginx-demo/Dockerfile`
- `project/nginx-demo/index.html`
- `sop/aws-ec2-setup.md`
- `sop/nginx-install-on-ec2.md`
- `sop/docker-exec-nginx.md`
- `sop/docker-build-custom-nginx.md`
- `sop/docker-run-nginx.md`

## Next Week

- Complete custom image build with Dockerfile
- Run container from self-built image
- Learn `docker logs`, `docker stop`, `docker rm`, and `docker images` more systematically
- Organize README and repository structure to match actual progress
- Resume AWS learning after account issue is resolved
