# Go + Gin Stack Preset

## Core Tech Stack
- **Language**: Go 1.21+
- **Web Framework**: Gin (`github.com/gin-gonic/gin`)
- **Config Management**: Viper (`github.com/spf13/viper`)
- **Database ORM**: GORM (`gorm.io/gorm`)
- **Logging**: Zap (`go.uber.org/zap`)
- **Dependency Management**: Go Modules

## Recommended Directory Structure (Standard Go Project Layout)
```text
.
├── cmd/
│   └── app/          # Application entry point (main.go)
├── internal/         # Private application and library code, not importable externally
│   ├── config/       # Config loading
│   ├── handler/      # HTTP request handling (Controllers)
│   ├── middleware/   # Gin middleware
│   ├── model/        # Database models and structs
│   ├── repository/   # Database interaction layer (DAO)
│   ├── route/        # Route registration
│   └── service/      # Core business logic layer
├── pkg/              # Reusable library code importable by external projects
│   ├── e/            # Unified error code definitions
│   ├── logger/       # Logging utility wrapper
│   └── response/     # Unified response wrapper
├── configs/          # Config file directory (e.g., config.yaml)
├── scripts/          # Build, install, analysis scripts
├── go.mod            # Go module file
└── Makefile          # Common Make commands
```

## Key Library References
- `github.com/gin-gonic/gin`: high-performance HTTP web framework.
- `gorm.io/gorm`: developer-friendly ORM library.
- `github.com/spf13/viper`: powerful configuration solution.
- `go.uber.org/zap`: high-performance logging library.
- `github.com/golang-jwt/jwt/v5`: JWT authentication.
