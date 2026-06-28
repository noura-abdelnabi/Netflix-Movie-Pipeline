# 🎬 Netflix Clone - DevSecOps CI/CD Pipeline

A fully automated DevSecOps Pipeline that builds, scans, and deploys a Netflix Clone application using modern DevOps tools and strict security practices.

---

## 🚀 Project Overview & Architecture

This project demonstrates a production-ready **CI/CD and DevSecOps pipeline** for a React-based Netflix web application. Every commit triggers automated security assessments before containerization and deployment and continuous resource monitoring.

### 🛠️ Tech Stack & Tools Used:
* **Automation Server:** Jenkins (Declarative Pipeline)
* **Code & Vulnerability Scanning:** OWASP Dependency-Check & Trivy (FS Scan)
* **Containerization:** Docker & DockerHub
* **Image Security:** Trivy (Image Scan)
* **Application API:** The Movie Database (TMDB) API
* **Metrics Collection (Monitoring):** Prometheus
* **Metrics Visualization (Dashboard):** Grafana

---

## ⚙️ Pipeline Stages & Deployment Steps

### 1️⃣ Security & Dependency Analysis
- **OWASP Dependency-Check:** Scans the project dependencies for publicly known vulnerabilities (CVEs).
 
  <img width="1900" height="739" alt="DP CHECK STEP 9" src="https://github.com/user-attachments/assets/e74ea6cd-8584-4556-b6d9-306db3d53198" />

- **Trivy FS Scan:** Analyzes the file system and source code for vulnerabilities and leaked secrets before building the image.

   <img width="1391" height="738" alt="SONAR QUBE STEP 8" src="https://github.com/user-attachments/assets/edd09efc-0830-4053-9abb-6475d87747af" />

### 2️⃣ Docker Build & Push
- The pipeline authenticates securely with **DockerHub**.
- Builds the production-ready Docker image while injecting the `TMDB_V3_API_KEY` argument dynamically to fetch real-time movie data.
- Tags and pushes the final image to DockerHub (`latest`).
<img width="923" height="669" alt="DOCKER IMAGE STEP 10" src="https://github.com/user-attachments/assets/752d2dfb-99e6-442a-bf9a-06cd17008eb8" />


### 3️⃣ Trivy Image Scanning
- Scans the generated Docker image layers to ensure no vulnerabilities are deployed to production.

### 4️⃣ Deployment
- Automatically spins up the Docker container, exposing the application on port **`8081`**.
<img width="1444" height="116" alt="NETFLIX CONTAIER" src="https://github.com/user-attachments/assets/d12a2a9c-0bef-4b61-a21b-bc651a8d66d4" />

---

## 📸 Screenshots & Live Proof

### 🚀 Running Application Dashboard
<img width="1600" height="822" alt="netflix app" src="https://github.com/user-attachments/assets/c60bc5dd-5cd6-4a5d-b0b7-18a153b74c98" />

### 📊 Prometheus & Grafana Monitoring
<img width="1916" height="876" alt="grafana dashboard node exporter step 4" src="https://github.com/user-attachments/assets/6b474aea-72b4-41eb-a73b-5e6f43495ec1" />

<img width="1907" height="882" alt="grafana dashboard jenkins step 5" src="https://github.com/user-attachments/assets/9cc2f495-8efa-4372-bc05-5b1d152d6f5d" />

<img width="1913" height="793" alt="prometheus targets step 5" src="https://github.com/user-attachments/assets/1e22580d-9679-46d5-8af7-9f88fb3533a6" />


### 🏗️ Jenkins Pipeline Success
<img width="1877" height="825" alt="PIPELINE STEP 10" src="https://github.com/user-attachments/assets/ae64c5e0-611f-419e-922b-08100a4a882c" />

---

## 🛠️ How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/noura-abdelnabi/Netflix-Movie-Pipeline.git](https://github.com/noura-abdelnabi/Netflix-Movie-Pipeline.git)
   cd Netflix-Movie-Pipeline
   ```

2. **Build the Docker Image:**
   ```bash
   docker build --build-arg TMDB_V3_API_KEY=your_tmdb_api_key -t netflix-clone .
    ```
 3. **Run the Container:**
    ```bash
    docker run -d -p 8081:80 --name netflix-app netflix-clone
    ```
  4. **Access the app at http://localhost:8081**

## ⚡ Maintained by Noura Abdelnabi | DevOps Enthusiast.
