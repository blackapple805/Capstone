# 🛡️ CyberGuardian — Cybersecurity Threat Detection & Response

CyberGuardian is an AI-assisted tool for real-time cybersecurity threat detection and response. It combines third-party threat-intelligence APIs with a full-stack web application to surface, contextualize, and help respond to potential threats from a single dashboard.

Built with **React**, **Node.js/Express**, and **MySQL**, fully containerized with **Docker**.

> Group capstone project. **Team:** [@YuukiCJ](https://github.com/YuukiCJ) · [@visioninhope](https://github.com/visioninhope) · [@blackapple805](https://github.com/blackapple805)

## My contributions

I worked across the full stack on this project — the React frontend (dashboard, threat-detection views, auth flow), the Node/Express backend and API, and the threat-detection logic. The team delivered the final in-person presentation in California while I contributed remotely from Paris.

## ✨ Features

- **Threat detection** powered by third-party threat-intelligence APIs (IPQualityScore, RapidAPI)
- **Dashboard** with an at-a-glance overview of detected threats and system status
- **User authentication** — secure signup, login, and protected routes (JWT)
- **Threat context views** for investigating individual findings
- **Technical plans & help sections** for guidance and documentation
- **Responsive React UI** with reusable components

## 🛠 Tech stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Backend | Node.js, Express |
| Database | MySQL |
| Auth | JSON Web Tokens (JWT) |
| Threat data | IPQualityScore API, RapidAPI services |
| Deployment | Docker, Docker Compose |

## 📁 Project structure

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
│   │   ├── components/      # Dashboard, ThreatDetection, Login, etc.
│   │   └── App.js
│   ├── Dockerfile
│   └── package.json
├── docker-compose.yml       # Orchestrates frontend, backend, and database
└── README.md
```

## 🚀 Getting started

### Prerequisites
- Docker and Docker Compose
- Node.js v16+ (only for local, non-Docker development)
- MySQL (handled by Docker, or install locally)

### Clone

```bash
git clone https://github.com/blackapple805/Capstone.git
cd Capstone
```

## 🔑 Environment variables

The backend requires several environment variables. Copy the example and fill in your own values:

```bash
cp backend/.env.example backend/.env
```

| Variable | Description |
|---|---|
| `PORT` | Port the backend server runs on (default 3001) |
| `DB_HOST` | MySQL host |
| `DB_NAME` | Database name |
| `DB_USER` | Database username |
| `DB_PASSWORD` | Database password |
| `SECRET_KEY` | Secret used to sign JWT auth tokens |
| `IPQUALITYSCORE_API_KEY` | API key for IPQualityScore threat lookups |
| `RAPIDAPI_KEY_2` | RapidAPI key for threat-intelligence services |
| `RAPIDAPI_KEY_3` | Additional RapidAPI key |

> Never commit your real `.env` — it's excluded via `.gitignore`. Only `.env.example` (with placeholder values) belongs in the repo.

## 🐳 Running with Docker

The simplest way to run the whole stack:

```bash
docker-compose up --build
```

Once the containers are up:
- Frontend: http://localhost:3000
- Backend API: http://localhost:3001

To stop everything:

```bash
docker-compose down
```

## 💻 Running locally (without Docker)

**Backend:**
```bash
cd backend
npm install
npm start
```

**Frontend** (separate terminal):
```bash
cd frontend
npm install
npm start
```

The frontend starts on http://localhost:3000 and proxies API requests to the backend on http://localhost:3001.

## 🧰 Troubleshooting

- **Database connection errors** — confirm your `DB_*` variables in `backend/.env` match your MySQL setup and that the database container is running.
- **API requests failing** — check that your threat-intelligence API keys are valid and not rate-limited.
- **Port already in use** — change `PORT` in `backend/.env`, or stop the process using that port.
- **Docker build issues** — run `docker-compose down` then `docker-compose up --build` to rebuild cleanly.

## 🙌 Credits

Developed as a group capstone. Team members:
- [@YuukiCJ](https://github.com/YuukiCJ)
- [@visioninhope](https://github.com/visioninhope)
- [@blackapple805](https://github.com/blackapple805)
