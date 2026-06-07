# Hi there, I'm Bartosz! 👋

### 🎓 Computer Science Student @ AGH | Full-Stack Software Engineer

Computer Science student at AGH University of Krakow with production experience shipping end-to-end systems independently — owning problem discovery, architecture, implementation, security, and deployment. Built 5 internal systems from scratch across backend, frontend, security, and containerized infrastructure. I start from open-ended problems, not specifications — and I see things through to production.

---

### 🛠️ Tech Stack & Tools

**Infrastructure & DevOps**

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/GNU%20Bash-4EAA25?style=for-the-badge&logo=GNU%20Bash&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white)
![Celery](https://img.shields.io/badge/celery-%2337814A.svg?style=for-the-badge&logo=celery&logoColor=white)

**Backend & Databases**

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

**Frontend & Mobile**

![Vue.js](https://img.shields.io/badge/vue.js-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D)
![React Native](https://img.shields.io/badge/react_native-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

**AI & Data**

![PaddleOCR](https://img.shields.io/badge/PaddleOCR-0062B0?style=for-the-badge&logo=paddlepaddle&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

**Networking (My Roots)**

![MikroTik](https://img.shields.io/badge/MikroTik-CD201F?style=for-the-badge&logo=MikroTik&logoColor=white)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=Wireshark&logoColor=white)

*TCP/UDP • SNMP • HTTP(S) • Firewalls • Routing*

---

### 🏢 Production Systems @ ERES Partner

#### 🧠 **Intelligent Document OCR Pipeline** — From Open Brief to Production
*AI-powered document processing system that eliminated driver registration errors.*
- **Brief:** Received a single open-ended ask — "reduce driver registration errors" — with no spec, no architecture, no prior system.
- **Architecture:** Designed end-to-end: PaddleOCR-based text extraction with a custom spatial indexing layer (BboxIndex) for label-proximity search across 7 document types (national ID front/back, driving licence, passport, residence card, student ID).
- **Preprocessing:** Type-specific pipelines — EXIF orientation correction, CLAHE contrast enhancement, resolution scaling.
- **Validation:** Cross-field PESEL/date consistency checks with structured per-field validation status returned via API.
- **Concurrency:** CPU-bound inference offloaded to thread-pool via `asyncio.run_in_executor` (backed by PaddleOCR's C++ core); async FastAPI + Celery orchestration for I/O; results cached in Redis with TTL.

#### 🔐 **ERES Vault** — Zero-Knowledge Secret Sharing
*End-to-end encrypted platform for sharing passwords, files, and messages.*
- **Crypto:** Client-side AES-256-GCM via WebCrypto API — server never sees the key or plaintext content.
- **Stack:** Vue 3 + Fastify + Redis, containerized with Docker Compose.
- **Features:** Configurable TTL, view limits, rate limiting, reverse-proxy-safe architecture.

#### 🎫 **Kiosk Ticketing System** — Full-Stack from Architecture to Deployment
*Walk-in visitor registration system running on Android tablets in kiosk mode.*
- **Stakeholders:** Worked directly with non-technical operators — listened to their workflows, translated feedback into requirements, and architected the system for extensibility so future needs wouldn't require structural rewrites.
- **Frontend:** React Native with OTP authentication via local SIM (Android SMS API).
- **Backend:** Stateless FastAPI with JWT + HMAC-SHA256 request signing, Android Keystore for key storage.
- **DevOps:** Dockerized across dev/stage/prod with compose overrides and `.env`-based config.

#### 🖥️ **Cross-Platform IT Inventory System**
*Automated hardware data collection across Windows, macOS, and Linux.*
- **Scripts:** PowerShell, zsh, and Bash with auto-elevation — employee runs one command, data lands on the server.
- **Backend:** FastAPI + PostgreSQL with admin dashboard and Vue.js instruction portal.

#### 📨 **Tax Document Automator** — PIT-11 & ZUS IMIR Distribution
*Automated email delivery of tax documents to 1500+ drivers.*
- **Pipeline:** Python + Celery + Redis task queue with SMTP/IMAP, async fleet API lookups, and deduplication.
- **Infra:** Fully containerized (Redis, worker, Flower monitoring) via Docker Compose.

---

### 🏆 Hackathons & Projects

#### 🥇 **[BITEhack 2026 — 1st Place] — Team Lead & Backend Architect**
*Location-aware city discovery app — won Classic Category at AGH University's BITEhack hackathon.*
- **Concept:** AI concierge powered by Google Gemini extracts user mood from conversation and generates swipeable "vibe" cards; venues filtered by GPS proximity using the Haversine formula.
- **My contribution (~65% of commits):** Async FastAPI backend architecture, JWT/OAuth2 + RBAC security layer, Gemini prompt engineering for structured JSON extraction, discovery matching engine with fallback logic, full frontend–backend integration (React + Vite).
- **DevOps:** Full containerization with Docker; PostgreSQL + Tortoise ORM.

#### 🥙 **[Krakowskie Kebaby] — Backend Lead & Project Manager**
*Engineering project focused on scalability and clean architecture.*
- **Backend:** Python + FastAPI, PostgreSQL with Tortoise ORM, schema migrations via Aerich.
- **DevOps:** Isolated Docker environments per service, `.env`-based multi-environment config.
- **Management:** Led a team of 4, managing tasks and sprints in ClickUp.

#### 📡 **Network Automation Scripts (AVSystem Intern)**
- Developed Python scripts to automate **MikroTik** router configuration (Firewall/IP/Routing) for production environments.

---

### 🌍 Currently / Coming Up

- 🏥 **AI in Healthcare Summer School** — Huazhong University of Science & Technology, Wuhan *(July 2026)*

---

### 📈 GitHub Stats

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=prbartosh&show_icons=true&theme=radical&hide_border=true" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=prbartosh&layout=compact&theme=radical&hide_border=true" height="150" alt="languages graph" />
</div>

---

### 📫 Connect with me

- **LinkedIn:** [Bartosz Pajor](https://linkedin.com/in/bartosz-pajor)
- **Email:** pajorb4@gmail.com

*"The best solutions start with the right questions — I'd rather spend an hour understanding the problem than a week solving the wrong one."* 🎯
