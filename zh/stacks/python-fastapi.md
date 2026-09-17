# Python + FastAPI 技术栈预设

## 核心技术栈
- **框架**: FastAPI
- **语言**: Python 3.10+
- **服务器**: Uvicorn (ASGI)
- **数据库 ORM**: SQLAlchemy 2.0
- **数据库迁移**: Alembic
- **数据校验**: Pydantic v2
- **测试**: pytest + httpx
- **依赖管理**: Poetry 或 pip-tools
- **代码格式化**: Ruff + Black

## 推荐目录结构 (分层架构)
```text
project/
├── alembic/              # 数据库迁移脚本
├── app/                  # 核心应用代码
│   ├── api/              # 路由层 (Endpoints, Controllers)
│   │   └── v1/
│   ├── core/             # 核心配置 (Config, Security, Logging)
│   ├── crud/             # 数据库操作层 (Create, Read, Update, Delete)
│   ├── db/               # 数据库连接与会话管理
│   ├── models/           # SQLAlchemy 数据库模型
│   ├── schemas/          # Pydantic 模型 (请求/响应结构)
│   ├── services/         # 业务逻辑层 (可选，适用于复杂业务)
│   ├── tests/            # pytest 测试用例
│   └── main.py           # FastAPI 应用入口
├── alembic.ini           # Alembic 配置文件
├── requirements.txt      # 依赖文件 (或 pyproject.toml)
└── .env                  # 环境变量文件
```

## 关键依赖列表
```text
fastapi>=0.110.0
uvicorn[standard]>=0.27.0
sqlalchemy>=2.0.27
alembic>=1.13.1
pydantic>=2.6.3
pydantic-settings>=2.2.1
asyncpg>=0.29.0  # 如果使用 PostgreSQL
pytest>=8.0.2
httpx>=0.27.0
```

## 日志配置与 API 文档
- **日志**: 建议在 `core/logger.py` 中配置 `logging.config.dictConfig`，标准输出 JSON 格式日志或集成结构化日志库如 `structlog`。
- **API 文档**: FastAPI 自动提供 `/docs` (Swagger UI) 和 `/redoc` (ReDoc)。使用 Pydantic 的 `Field` 注解为文档提供更详细的说明。
