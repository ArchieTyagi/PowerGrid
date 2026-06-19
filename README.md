# PowerGrid ⚡

A full-stack smart-meter analytics platform that helps electricity consumers
understand their usage, forecast future consumption, detect anomalies, and
optimize their bills against real DISCOM tariff structures.

**Live demo:** https://power-grid-ruddy.vercel.app/

> Built as a two-person On-the-Job Training (OJT) project at **Polaris School of
> Technology**. I owned the **React frontend end-to-end** and have since worked
> through the full **ML/Python pipeline**, so I can speak to the entire system
> architecture — frontend, backend, and the forecasting/anomaly-detection layer.

---

## My Contribution

**Frontend (owned end-to-end):**
- Built the entire React + Vite application — landing page through to the full dashboard
- Designed a tabbed dashboard: Overview, Analytics, Billing, Compare, ML, Rewards, Profile
- Wrote custom data-fetching hooks (`useDashboardData`, `useMLData`, `useConsumptionData`, `useBilling`, `useComparison`, `useGamification`, `useHeatmap`)
- Implemented auth flows (OAuth + phone OTP) with Supabase integration
- Built the API client layer and wired the frontend to live backend data + WebSocket updates
- Added polish: animated landing page, custom cursor, scroll-reveal effects

**ML/Backend (studied in depth, can explain fully):**
- Worked through the FastAPI service architecture (routers / services / models / schemas)
- Understand the forecasting and anomaly-detection pipeline (scikit-learn) end to end
- Familiar with the DISCOM slab-based tariff/billing logic and the WebSocket real-time layer

---

## What it does

- **Consumption analytics** — interactive dashboards, heatmaps, and time-series views
- **Forecasting** — predicts future consumption using statistical and ML models
- **Anomaly detection** — flags unusual usage patterns automatically
- **Smart billing** — calculates bills against Indian DISCOM tariff slabs
- **Comparison** — benchmark usage across periods and against similar users
- **Gamification** — rewards and engagement layer to encourage efficient usage
- **Real-time updates** — live data over WebSocket

---

## Architecture
Frontend (React + Vite)  ──HTTP/WebSocket──>  Backend (FastAPI)

│                                            │

Dashboard, Auth,                          Routers · Services · Models

Charts, Hooks                                     │

ML pipeline (forecasting,

anomaly detection, tariffs)

│

PostgreSQL + Supabase
---

## Tech Stack

**Frontend:** React, Vite, Supabase JS
**Backend:** FastAPI, SQLAlchemy, Alembic, scikit-learn
**Database:** PostgreSQL, Supabase
**Infra:** Docker, Vercel (frontend), Render (backend)
**Testing:** pytest, Vitest

---

## Getting Started

### Frontend
```bash
npm install
cp .env.example .env
npm run dev
```

### Backend
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
alembic upgrade head
python -m app.seed.run_seed
uvicorn app.main:app --reload
```

---

## Team
Two-person OJT project. Frontend by **Archi Tyagi** (me). Backend & ML built collaboratively with my OJT partner; I've since gone deep on the ML side.