# Go + Gin 技术栈预设

## 核心技术栈
- **语言**: Go 1.21+
- **Web 框架**: Gin (`github.com/gin-gonic/gin`)
- **配置管理**: Viper (`github.com/spf13/viper`)
- **数据库 ORM**: GORM (`gorm.io/gorm`)
- **日志**: Zap (`go.uber.org/zap`)
- **依赖管理**: Go Modules

## 推荐目录结构 (Standard Go Project Layout)
```text
.
├── cmd/
│   └── app/          # 应用程序的主入口点 (main.go)
├── internal/         # 私有应用和库代码，外部不能导入
│   ├── config/       # 配置加载
│   ├── handler/      # HTTP 请求处理 (Controllers)
│   ├── middleware/   # Gin 中间件
│   ├── model/        # 数据库模型与结构体
│   ├── repository/   # 数据库交互层 (DAO)
│   ├── route/        # 路由注册
│   └── service/      # 核心业务逻辑层
├── pkg/              # 可以被外部项目导入的通用库代码
│   ├── e/            # 错误码统一定义
│   ├── logger/       # 日志工具封装
│   └── response/     # 统一响应封装
├── configs/          # 配置文件目录 (如 config.yaml)
├── scripts/          # 构建、安装、分析等脚本
├── go.mod            # Go module 文件
└── Makefile          # 常用的 Make 命令
```

## 关键库参考
- `github.com/gin-gonic/gin`: 高性能 HTTP Web 框架。
- `gorm.io/gorm`: 开发者友好的 ORM 库。
- `github.com/spf13/viper`: 强大的配置解决方案。
- `go.uber.org/zap`: 高性能日志库。
- `github.com/golang-jwt/jwt/v5`: JWT 认证。
