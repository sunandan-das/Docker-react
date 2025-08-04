# 🚀 DevOps CI/CD Pipeline: Dockerized React App to AWS Elastic Beanstalk

[![Deploy Frontend](https://github.com/sunandan-das/Docker-react/actions/workflows/deploy.yaml/badge.svg?branch=main)](https://github.com/sunandan-das/Docker-react/actions/workflows/deploy.yaml)


> **DevOps Portfolio Project** | GitHub Actions | Docker | AWS Elastic Beanstalk | CI/CD Automation

This project demonstrates a **production-grade CI/CD pipeline** that builds, tests, and deploys a Dockerized React app to **AWS Elastic Beanstalk** using **GitHub Actions**.

---

## ✅ Features

* Fully automated CI/CD pipeline with GitHub Actions
* Containerized React app using Docker
* Deployment artifact packaging and delivery to AWS
* Secrets managed via GitHub encrypted secrets
* Resume-ready infrastructure project

---

## 🧰 Tech Stack

| Tool                  | Purpose            |
| --------------------- | ------------------ |
| React                 | Frontend framework |
| Docker                | Containerization   |
| GitHub Actions        | CI/CD pipeline     |
| AWS Elastic Beanstalk | Hosting platform   |
| S3                    | Artifact storage   |
| EC2                   | Underlying compute |

---

## 📦 Installation & Local Setup

```bash
# Clone the repo
git clone https://github.com/sunandan-das/Docker-react.git
cd Docker-react

# Install dependencies
npm install

# Start app locally
npm start

# Or using Docker
docker build -f Dockerfile.dev -t react-app .
docker run -p 3000:3000 react-app
```

---

## 🛠️ CI/CD Pipeline Breakdown

GitHub Actions file: `.github/workflows/deploy.yml`

### Steps:

1. ✅ Checkout the code
2. ✅ Build Docker image using `Dockerfile.dev`
3. ✅ (Optional) Run tests
4. ✅ Copy `Dockerfile.dev` → `Dockerfile`
5. ✅ Package code into `deploy.zip`
6. ✅ Upload and deploy to AWS Elastic Beanstalk

---

## 🌍 AWS Configuration Guide

### 1. **Create Elastic Beanstalk App**

* Go to [Elastic Beanstalk Console](https://console.aws.amazon.com/elasticbeanstalk)
* Create application: `react-app`
* Platform: **Docker running on 64bit Amazon Linux**
* Environment: `React-env`
* Region: `eu-north-1`

### 2. **Create an S3 Bucket**

* Name: `elasticbeanstalk-eu-north-1-your-account-id`
* Region: `eu-north-1`

### 3. **Create IAM User for GitHub Actions**

* Attach policy: `AWSElasticBeanstalkFullAccess`, `AmazonS3FullAccess`
* Save `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`

### 4. **Add GitHub Secrets**

Go to GitHub > Repo > Settings > Secrets:

| Name                    | Purpose                           |
| ----------------------- | --------------------------------- |
| `AWS_ACCESS_KEY_ID`     | IAM key with EBS + S3 permissions |
| `AWS_SECRET_ACCESS_KEY` | IAM secret for deployment access  |

---

## 📁 Project Structure

```plaintext
.
├── Dockerfile.dev           # Used in CI for build & test
├── Dockerfile               # Used by EBS to run app
├── .github/workflows/       # GitHub Actions config
├── src/                     # React source code
├── public/                  # Static files
├── package.json             # Dependencies and scripts
├── deploy.yml               # CI/CD workflow
└── README.md                # This documentation
```

---

## 🎯 Deployment Guide

```bash
# 1. Push to main
$ git push origin main

# 2. GitHub Actions builds/tests/zips/deploys

# 3. Access the live app
http://React-env.eba-XXXX.eu-north-1.elasticbeanstalk.com/
```

---

## 📈 Resume-Ready Summary

> **"Built and deployed a containerized React app via GitHub Actions CI/CD pipeline to AWS Elastic Beanstalk with automated workflows, versioned artifacts, and secure IAM integration."**

---

## 👨‍💻 Author

**Sunandan Sekhar Das**
📍 Dublin, Ireland
🔗 [LinkedIn](https://www.linkedin.com/in/sunandansekhardas/)

---

