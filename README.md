# Zenve Business Intelligence Platform

Zenve BI is an integrated executive and operational business intelligence platform engineered for enterprise healthcare, pharmacy, veterinary services, and multi-channel commerce.

---

## Architecture Overview

- **Frontend**: React 18 SPA bundled with Vite, modern glassmorphism dashboards, KPI scorecards, interactive charts, and real-time proxying.
- **Backend**: FastAPI (Python 3.14 / ASGI) delivering high-throughput RESTful APIs, ML predictive engines (Sales forecast, Churn, Inventory demand), and Copilot RAG pipeline.
- **Database**: Multi-tenant relational schema supporting MySQL 8.0 with automatic SQLite (`zenvebi.db`) fallback loaded with 25+ domain tables.

---

## Quick Start

### 1. Automated Platform Startup
Run the platform launcher:
```bat
START_ZENVE.bat
```
This automatically initiates both the FastAPI backend on port `8000` and the Vite dev server on port `3001`.

### 2. Manual Startup

#### Backend
```powershell
cd backend
python -m uvicorn app.main:app --reload --port 8000 --host 127.0.0.1
```
- API Documentation (Swagger): [http://127.0.0.1:8000/api/docs](http://127.0.0.1:8000/api/docs)
- Health Check: [http://127.0.0.1:8000/api/health](http://127.0.0.1:8000/api/health)

#### Frontend
```powershell
cd frontend
npm install
npm run dev
```
- Web Application: [http://localhost:3001](http://localhost:3001)

---

## Repository Structure

```
├── backend/
│   ├── app/
│   │   ├── api/v1/         # Endpoints & route handlers
│   │   ├── core/           # Config & database connection
│   │   ├── ml/             # ML prediction pipelines & models
│   │   ├── models/         # SQLAlchemy ORM models
│   │   ├── rag/            # Vector store & RAG engine
│   │   └── services/       # Business intelligence services
│   ├── artifacts/          # Trained models & catalogs
│   ├── zenvebi.db          # Embedded database
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── src/                # React components & domain dashboards
│   ├── public/             # Static assets & dashboard styles
│   ├── package.json        # Dependencies & scripts
│   └── vite.config.js      # Reverse proxy configuration
├── database/
│   └── init/               # SQL schemas (01_schema.sql, 03_full_schema.sql)
└── START_ZENVE.bat         # Single-click orchestration script
```

---

## License
Proprietary — Zenve Intelligence Engine.
