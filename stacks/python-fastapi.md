# Python + FastAPI Stack Preset

## Core Tech Stack
- **Framework**: FastAPI
- **Language**: Python 3.10+
- **Server**: Uvicorn (ASGI)
- **Database ORM**: SQLAlchemy 2.0
- **DB Migration**: Alembic
- **Validation**: Pydantic v2
- **Testing**: pytest + httpx
- **Dependency Management**: Poetry or pip-tools
- **Formatting**: Ruff + Black

## Recommended Directory Structure (Layered Architecture)
```text
project/
├── alembic/              # Database migration scripts
├── app/                  # Core application code
│   ├── api/              # Route layer (Endpoints, Controllers)
│   │   └── v1/
│   ├── core/             # Core config (Config, Security, Logging)
│   ├── crud/             # Database operation layer (Create, Read, Update, Delete)
│   ├── db/               # DB connection and session management
│   ├── models/           # SQLAlchemy database models
│   ├── schemas/          # Pydantic models (request/response structures)
│   ├── services/         # Business logic layer (optional, for complex business)
│   ├── tests/            # pytest test cases
│   └── main.py           # FastAPI app entry point
├── alembic.ini           # Alembic config file
├── requirements.txt      # Dependency file (or pyproject.toml)
└── .env                  # Environment variable file
```

## Key Dependencies
```text
fastapi>=0.110.0
uvicorn[standard]>=0.27.0
sqlalchemy>=2.0.27
alembic>=1.13.1
pydantic>=2.6.3
pydantic-settings>=2.2.1
asyncpg>=0.29.0  # If using PostgreSQL
pytest>=8.0.2
httpx>=0.27.0
```

## Logging & API Docs
- **Logging**: configure `logging.config.dictConfig` in `core/logger.py`, output JSON logs to stdout, or integrate a structured logging library like `structlog`.
- **API Docs**: FastAPI auto-provides `/docs` (Swagger UI) and `/redoc` (ReDoc). Use Pydantic's `Field` annotations to give the docs more detail.
