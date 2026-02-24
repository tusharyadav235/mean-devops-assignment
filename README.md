# MEAN Stack DevOps Assignment

## Project Overview
A full-stack MEAN application containerized with Docker and deployed via a GitHub Actions CI/CD pipeline.

## Infrastructure Details
- **Cloud Provider:** AWS (EC2 Instance)
- **Containerization:** Docker & Docker Compose
- **Web Server:** Nginx (configured as a Reverse Proxy and SPA router)
- **CI/CD:** GitHub Actions

## Setup & Deployment Instructions
1. **Clone the repo:** `git clone <your-repo-link>`
2. **Local Development:** Run `docker-compose up --build` to start the stack locally.
3. **Production Deployment:** - Changes pushed to the `main` branch trigger the GitHub Action.
   - The workflow builds images, pushes to Docker Hub, and deploys to the EC2 instance.

## Nginx Configuration
To handle Angular's client-side routing and prevent 404 errors on refresh, the following `try_files` directive was implemented:
`try_files $uri $uri/ /index.html;`
