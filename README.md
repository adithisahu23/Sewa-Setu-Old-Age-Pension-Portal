# 🏛️ Seva Setu — Old Age Pension Portal

**A digital pension application portal designed to simplify access to old-age pension services.**

Seva Setu is a web-based portal for the Old Age Pension Scheme of the fictional Department of Social Welfare, Government of Purvanchal. It provides a centralized interface for citizens to apply for pension benefits and check their application status.

🔗 **Live Website:** [Add your public deployment URL here]

💻 **Local Website:** http://localhost:8000

---

## 📌 Project Overview

The Seva Setu Old Age Pension Portal aims to make pension-related services more accessible through a simple digital interface. Eligible senior citizens can use the portal to begin their pension application process, verify their mobile number, submit personal and banking information, upload supporting documents, and track application status.

The application runs using Docker Compose and includes a web application, PostgreSQL database, scheduler, and SMS gateway service.

## ✨ Features

- **🏠 Citizen Homepage:** Provides an overview of the pension scheme and application instructions.
- **📝 Pension Application:** Interface for citizens to initiate a pension application.
- **📱 OTP Verification:** Supports mobile-number verification as part of the application process.
- **📄 Document Upload:** Supports age-proof documents in JPG or PDF format, with a stated maximum file size of 5 MB.
- **🔎 Application Status:** Allows users to check the status of their pension application.
- **🗄️ PostgreSQL Database:** Provides persistent database storage for application data.
- **⚙️ Background Scheduler:** Includes a scheduler service for background processing.
- **📨 SMS Gateway:** Includes an SMS gateway service for messaging-related functionality.
- **🐳 Dockerized Architecture:** Runs the application and supporting services through Docker Compose.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application and backend services |
| Flask / Gunicorn | Web application serving |
| PostgreSQL | Relational database |
| Docker | Containerization |
| Docker Compose | Multi-service orchestration |
| SMS Gateway | Messaging and OTP-related functionality |

## 🖥️ Application Preview

The homepage presents the pension scheme information, an application deadline notice, and two main actions:

- **Apply for Pension**
- **Check Application Status**

The portal also provides step-by-step instructions for mobile verification, filling out the application form, uploading age-proof documents, and submitting the declaration.

## 🚀 Getting Started

### Prerequisites

Install the following tools before running the project:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Git](https://git-scm.com/downloads)

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

### 2. Start Docker Desktop

Ensure Docker Desktop is running and its container engine is ready.

### 3. Start the application

From the directory containing `docker-compose.yml`, execute:

```bash
docker compose up -d --build
```

### 4. Verify the containers

```bash
docker compose ps
```

Confirm that the application and its supporting services are running.

### 5. Open the website

Visit:

http://localhost:8000

### 6. View application logs

```bash
docker compose logs --tail=100 app
```

To inspect the SMS gateway logs:

```bash
docker compose logs --tail=100 smsgw
```

### 7. Stop the application

```bash
docker compose down
```

To stop the services and remove the containers while preserving the default named database volume:

```bash
docker compose down
```

**Note:** Avoid using `docker compose down -v` unless you intentionally want to remove the associated named volumes and potentially delete local database data.

## 🏗️ Architecture

The project uses a multi-container architecture orchestrated by Docker Compose.

```text
Citizen
   |
   v
Web Browser
   |
   v
Web Application
   |
   +------> PostgreSQL Database
   |
   +------> SMS Gateway
   |
   +------> Background Scheduler
```

The web application handles browser requests, PostgreSQL provides database storage, and the supporting services provide messaging and background-processing capabilities.

## 🔐 Security Considerations

- Do not commit passwords, API keys, database credentials, or secret environment files to GitHub.
- Use environment variables or a secrets manager for sensitive configuration.
- Validate uploaded files and enforce file-size limits on the server.
- Apply access controls to application data and officer-only functionality.
- Use HTTPS for public deployments.
- Configure OTP expiry, attempt limits, and rate limiting before production use.
- Verify the SMS provider configuration before relying on real SMS delivery.

## 🌐 Deployment

The local development address, `http://localhost:8000`, is not accessible to other users over the public internet.

To make the website publicly accessible:

1. Choose a hosting platform that supports Docker containers.
2. Configure the required environment variables and database connection.
3. Deploy the application and its supporting services.
4. Configure HTTPS and any required persistent storage.
5. Test the application using the generated public URL.
6. Replace the Live Website placeholder at the top of this README with the verified public URL.

Ensure the database and any required background services are deployed correctly; running only the web container may not provide the full application functionality.

## 🧪 Testing Checklist

- [ ] Homepage loads successfully.
- [ ] Pension application form opens.
- [ ] OTP verification works as configured.
- [ ] Document upload accepts supported file types.
- [ ] Application submissions are saved correctly.
- [ ] Application status lookup works.
- [ ] Background scheduler operates as expected.
- [ ] SMS gateway behavior is verified.
- [ ] Public deployment works over HTTPS.

## ⚠️ Important Note

This project uses a fictional government department and jurisdiction for demonstration purposes. It should not be interpreted as an official government website or a real pension-benefit service.

Before production use, verify all eligibility rules, security controls, data-protection requirements, and messaging integrations.

## 👩‍💻 Author

**Aditi Sahu**

B.Tech — Data Science

GitHub: [@adithisahu23](https://github.com/adithisahu23)

---

⭐ If you find this project useful, consider starring the repository!
