<div align="center">

# ⚖️ TradeMarkia Assignment

**A FastAPI backend assignment — clean architecture, async Postgres, background workers.**

![FastAPI](https://img.shields.io/badge/API-FastAPI-009688?logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/DB-PostgreSQL%20(asyncpg)-4169E1?logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Infra-Docker%20Compose-2496ED?logo=docker&logoColor=white)

</div>

---

## 📖 About

My submission for the TradeMarkia backend assignment: a FastAPI service structured by modules (auth, workers), backed by async PostgreSQL, with Docker Compose for one-command startup and a pytest suite included.

> 🚧 **Status:** project scaffolding and module layout are in place; feature endpoints are being implemented.

## 🏗️ Architecture

```
backend/app/
├── api/v1/          # Versioned REST endpoints
├── modules/auth/    # Authentication module
├── worker/          # Background task workers
├── core/            # Config & shared utilities
├── db/db.py         # Database session management
└── tests/           # Test suite
```

## 🚀 Getting Started

### Prerequisites

- Python 3.12+ with [`uv`](https://docs.astral.sh/uv/)
- Docker & Docker Compose

### Run with Docker

```sh
git clone https://github.com/tanishqsrivastavaa/TradeMarkia-Assignment.git
cd TradeMarkia-Assignment
cp .env.example .env    # fill in values
docker compose up --build
```

### Run locally

```sh
uv sync
cp .env.example .env
uv run uvicorn main:app --reload
```

### Environment

Key variables (see `.env.example`):

| Variable | Purpose |
|---|---|
| `DATABASE_URL` | Async Postgres connection (`postgresql+asyncpg://…`) |
| `SECRET_KEY` | Auth signing secret |
| `APP_ENV` / `APP_DEBUG` / `APP_PORT` | App configuration |

## 🧪 Tests

```sh
uv run pytest backend/tests/
```
