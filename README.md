# 🌐 CyberGuardian — Cybersecurity Threat Detection & Response Tool

CyberGuardian is an AI-powered tool for real-time cybersecurity threat detection and
response. It combines third-party threat-intelligence APIs with a full-stack web
application to surface, contextualize, and help respond to potential threats from a
single dashboard.

Built with **React**, **Node.js/Express**, and **MySQL**, and fully containerized
with **Docker**.

> **Group capstone project** based on the
> [Sidequest040/Capstone](https://github.com/Sidequest040/Capstone) template.
>
> **Team:** [@YuukiCJ](https://github.com/YuukiCJ) · [@visioninhope](https://github.com/visioninhope) · [@blackapple805](https://github.com/blackapple805)

---

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Running with Docker](#-running-with-docker)
- [Running Locally (without Docker)](#-running-locally-without-docker)
- [Troubleshooting](#-troubleshooting)
- [Credits](#-credits)

---

## ✨ Features

- **Threat detection** powered by third-party threat-intelligence APIs (IPQualityScore, RapidAPI)
- **Dashboard** with an at-a-glance overview of detected threats and system status
- **User authentication** — secure signup, login, and protected routes (JWT)
- **Threat context** views for investigating individual findings
- **Technical plans & help** sections for guidance and documentation
- **Responsive React UI** with reusable components

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React.js |
| Backend | Node.js, Express |
| Database | MySQL |
| Auth | JSON Web Tokens (JWT) |
| Threat data | IPQualityScore API, RapidAPI services |
| Deployment | Docker, Docker Compose |

## 📁 Project Structure

```
Capstone/
├── backend/                 # Node/Express API
│   ├── server.js            # API entry point
│   ├── Dockerfile
│   ├── .env.example         # Template for required environment variables
│   └── package.json
├── frontend/                # React application
│   ├── public/
│   ├── src/
│   │   ├── components/       # Dashboard, ThreatDetection, Login, etc.
│   │   └── App.js
│   ├── Dockerfile
│   └── package.json
├── docker-compose.yml       # Orchestrates frontend, backend, and database
└── README.md
```

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- [Docker](https://www.docker.com/) and Docker Compose
- [Node.js](https://nodejs.org/) (v16 or higher) — only needed for local, non-Docker development
- [MySQL](https://www.mysql.com/) — handled by Docker, or install locally for development

### Clone the repository

```bash
git clone https://github.com/blackapple805/Capstone.git
cd Capstone
```

## 🔑 Environment Variables

The backend requires several environment variables. Copy the example file and fill in
your own values:

```bash
cp backend/.env.example backend/.env
```

| Variable | Description |
|----------|-------------|
| `PORT` | Port the backend server runs on (default `3001`) |
| `DB_HOST` | MySQL host |
| `DB_NAME` | Database name |
| `DB_USER` | Database username |
| `DB_PASSWORD` | Database password |
| `SECRET_KEY` | Secret used to sign JWT auth tokens |
| `IPQUALITYSCORE_API_KEY` | API key for IPQualityScore threat lookups |
| `RAPIDAPI_KEY_2` | RapidAPI key for threat-intelligence services |
| `RAPIDAPI_KEY_3` | Additional RapidAPI key |

> **Never commit your real `.env` file** — it is excluded via `.gitignore`. Only
> `.env.example` (with placeholder values) belongs in the repository.

## 🐳 Running with Docker

The simplest way to run the whole stack (frontend, backend, and database):

```bash
docker-compose up --build
```

Once the containers are up:

- Frontend: <http://localhost:3000>
- Backend API: <http://localhost:3001>

To stop everything:

```bash
docker-compose down
```

## 💻 Running Locally (without Docker)

**Backend:**

```bash
cd backend
npm install
npm start
```

**Frontend** (in a separate terminal):

```bash
cd frontend
npm install
npm start
```

The frontend will start on <http://localhost:3000> and proxy API requests to the
backend on <http://localhost:3001>.

## 🧰 Troubleshooting

- **Database connection errors** — confirm your `DB_*` variables in `backend/.env`
  match your MySQL setup, and that the database container/service is running.
- **API requests failing** — check that your threat-intelligence API keys are valid
  and not rate-limited.
- **Port already in use** — change the `PORT` value in `backend/.env`, or stop the
  process using that port.
- **Docker build issues** — try `docker-compose down` followed by
  `docker-compose up --build` to rebuild cleanly.

## 🙌 Credits

This project was developed as a **group capstone** based on the
[Sidequest040/Capstone](https://github.com/Sidequest040/Capstone) template.

**Team members:**

- [@YuukiCJ](https://github.com/YuukiCJ)
- [@visioninhope](https://github.com/visioninhope)
- [@blackapple805](https://github.com/blackapple805)
