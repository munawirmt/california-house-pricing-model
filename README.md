# California House Price Prediction API

An end-to-end Machine Learning web application that predicts median house values in California based on various demographic and geographic features. This project is built using Scikit-Learn, containerized with Docker, and deployed on Render.

Live Demo: https://onrender.com

---

## Software and Tools Requirements

1. GitHub Account (https://github.com) - For version control and deployment.
2. Render Account (https://render.com) - For hosting the Dockerized production API.
3. VS Code IDE (https://visualstudio.com) - Recommended code editor.
4. Git CLI (https://git-scm.com) - For pushing code to GitHub.
5. Docker Desktop (https://docker.com) - For local container testing.

---

## Local Development Setup

Follow these steps to run the project locally on your machine:

### 1. Environment Isolation (Using Conda)
Create a clean virtual environment using the local Python environment:
```bash
conda create -p venv python==3.12.7 -y
conda activate venv/
```

### 2. Install Dependencies
Install all required machine learning and web server packages:
```bash
pip install -r requirements.txt
```

### 3. Run the Web Server Locally
```bash
python app.py
```

---

## Docker Production Setup

To test the production container locally before deploying to Render:

### 1. Build the Docker Image
```bash
docker build -t california-housing-app .
```

### 2. Run the Container
```bash
docker run -d -p 5000:5000 -e PORT=5000 california-housing-app
```
Access the local API at http://localhost:5000.

---

## Continuous Deployment to Render

This project is configured for Git-triggered automatic deployments on Render via Docker:
1. Every time code is pushed to the main branch on GitHub, Render triggers a new build.
2. Render reads the Dockerfile, installs optimization layers using python:3.12-slim, and dynamically assigns a traffic port using Gunicorn.
