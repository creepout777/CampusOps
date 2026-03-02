# CampusOps

> Academic Management & Automation Platform under the supervision of Dr Ahmed Amamou

A full-stack web application for managing academic planning, attendance, progress tracking, and payments with automated workflows.

---

## Overview

CampusOps centralizes academic operations for educational institutions, providing:

- **Planning** - Schedule management with calendar views
- **Attendance** - Presence/absence tracking and statistics  
- **Progress** - Module advancement monitoring
- **Payments** - Tuition and installment tracking
- **Automation** - OpenClaw workflows, Telegram bot, email notifications

---

## Tech Stack

**Backend:** Spring Boot 3.2, Java 17, PostgreSQL, Spring Security (JWT)  
**Frontend:** React 18, Axios, Tailwind CSS  
**Integration:** OpenClaw, Telegram API, IMAP/SMTP

---

## Quick Start

### Prerequisites

- Java 17+
- Node.js 18+
- PostgreSQL 14+
- Maven 3.8+
- Git

### Installation
```bash
# Clone repository
git clone https://github.com/YOUR-ORG/campusops.git
cd campusops

# Switch to develop branch
git checkout develop
git pull origin develop
```

### Run Backend
```bash
cd backend
mvn clean install
mvn spring-boot:run
```

Backend runs on `http://localhost:8080`

### Run Frontend
```bash
cd frontend
npm install
npm start
```

Frontend runs on `http://localhost:3000`

---

## Project Structure
```
campusops/
├── backend/           # Spring Boot API
├── frontend/          # React application
├── docs/              # Documentation
│   └── developer-guide.pdf
├── scripts/           # Deployment scripts
└── README.md
```

---

## Documentation

### 📘 Developer Guide

**All team members must read:** [Developer Guide](docs/Semester_Course_Project_Team_Instructions.pdf)

This guide contains:
- Setup instructions
- Git workflow
- Daily commands
- Error handling
- Team rules

### Additional Docs

- API Documentation: `docs/api/` *(coming soon)*
- Database Schema: `docs/architecture/` *(coming soon)*
- OpenClaw Workflows: `docs/workflows/` *(coming soon)*

---

## Git Workflow

### Branches

- `main` - Production code (protected)
- `develop` - Active development (protected)

### Daily Workflow
```bash
# Start work
git checkout develop
git pull origin develop

# End work
git add .
git commit -m "description"
git pull origin develop
git push origin develop
```

### Rules

- Work on `develop` branch only
- Pull before starting work
- Commit with clear messages
- Never push to `main`
- Never use `--force`

**For complete workflow, see [Developer Guide](docs/developer-guide.pdf)**

---

## Configuration

### Backend Environment
```yaml
# application.yml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/campusops
    username: ${DB_USERNAME}
    password: ${DB_PASSWORD}
  
  mail:
    host: ${SMTP_HOST}
    username: ${SMTP_USERNAME}
    password: ${SMTP_PASSWORD}

telegram:
  bot:
    token: ${TELEGRAM_BOT_TOKEN}
```

### Frontend Environment
```env
# .env
REACT_APP_API_URL=http://localhost:8080/api
```

**Never commit `.env` files**



---

## Deployment

Deployment to Contabo VPS is handled by the Project Manager via CI/CD pipelines.

---
