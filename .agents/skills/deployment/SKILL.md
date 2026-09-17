---
name: deployment
description: >-
  当用户要求部署、上线、发布、构建生产版本、
  或进行发布前检查时激活。覆盖从预检到上线后验证的完整流程。
---

# 部署上线

从预检清单到生产部署的完整自动化流程。

## 步骤

### 1. 预部署检查

依次运行以下检查，**任何一项失败则中止部署**：

```bash
# 1. 测试必须全部通过
pnpm test
# 或 pytest

# 2. Lint 检查
pnpm lint

# 3. 类型检查
pnpm typecheck

# 4. 构建不能有错误
pnpm build
```

额外检查：
- [ ] `STATUS.md` 中无未解决的阻塞性问题
- [ ] 无硬编码的密钥或环境变量
- [ ] 数据库迁移已准备（如适用）

### 2. 构建生产版本

```bash
# 前端
NODE_ENV=production pnpm build

# 后端
# 确认 Dockerfile 或部署脚本存在
```

### 3. 环境配置检查

- 确认目标环境的环境变量已配置
- 确认数据库连接可用
- 确认第三方服务 API 密钥有效
- 确认域名和 SSL 证书就绪（生产环境）

### 4. 执行部署

按照项目配置的部署方式执行：
- Docker Compose / Kubernetes
- 云平台（Vercel / Railway / 阿里云等）
- 自定义部署脚本（`scripts/deploy.sh`）

### 5. 部署后验证

- [ ] 服务健康检查通过
- [ ] 关键 API 端点响应正常
- [ ] 前端页面可正常访问
- [ ] 日志无异常错误

### 6. 更新文档

- 更新 `STATUS.md` 中的当前阶段
- 更新 `docs/CHANGELOG.md` 添加发布记录
- 标记 Git 版本标签：`git tag v<版本号>`
