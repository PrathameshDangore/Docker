# Student Management Dockerized Application (3-Tier Architecture):
  This project is a full Docker-based deployment of a 3-tier Student Management System consisting of:
  Frontend (FE) – Nginx hosting HTML/CSS/JS
  Backend (BE) – Java/Spring Boot (or Node/Express, depending on project)
  Database (DB) – MySQL running as a Docker container

# Tech Stack:
  1) Docker
  2) Docker Compose 
  3) Nginx
  4) Java / Spring Boot (or Node backend)
  5) AWS EC2
  6) AWS RDS (Mariadb)


1️⃣ Install Docker:
    => apt update  
    => sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

2️⃣ Clone Repository:
    => git clone https://github.com/Anilbamnote/cdec-46.git

3️⃣ Build and Run MySQL (DB) Container:

    => cd Docker/student-docker/DB

    => docker build -t db-image:v1 .

    => docker run -d -p 3306:3306 --name db-cont db-image:v1

4️⃣ Backend Service Build & Run:

    => cd ../BE

    => docker build -t bk-image:v1 .

    => docker run -d -p 8080:8080 --name bk-cont bk-image:v1

5️⃣ Frontend Build & Run:

    => cd ../FE

    => docker build -t fe-image:v1 .

    => docker run -d -p 80:80 --name fe-cont fe-image:v1

6️⃣ Verify:

    => docker ps -a


# System Architecture
            ┌──────────────────────────────┐
            │            Frontend          │
            │        (Nginx Container)     │
            └───────────────▲──────────────┘
                            │
                            ▼
            ┌──────────────────────────────┐
            │            Backend           │
            │   (Spring Boot Container)    │
            └───────────────▲──────────────┘
                            │
                            ▼
            ┌──────────────────────────────┐
            │        Database Layer        │
            │ Docker MySQL (Local) / RDS   │
            └──────────────────────────────┘



