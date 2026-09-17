---
name: code-quality
description: >-
  当用户要求代码检查、lint、代码审查、质量扫描、安全审计、
  或代码规范检查时激活。运行完整的代码质量检查流程并输出报告。
---

# 代码质量检查

运行完整的代码质量检查流程，涵盖代码风格、类型安全、安全漏洞和编码规范。

## 步骤

### 1. 代码风格检查（Lint）

```bash
# 前端
pnpm lint                     # ESLint 检查
pnpm lint --fix               # 自动修复

# 后端
ruff check .                  # Ruff 检查
ruff check . --fix            # 自动修复
```

### 2. 类型检查

```bash
# 前端
pnpm typecheck                # TypeScript 类型检查

# 后端
mypy app/                     # Python 类型检查（如已配置）
```

### 3. 安全审计

```bash
# 依赖漏洞扫描
pnpm audit                    # npm 依赖
pip-audit                     # Python 依赖

# 代码中的安全隐患
# 检查硬编码密钥：grep -rn "password\|secret\|api_key" --include="*.py" --include="*.ts"
```

### 4. 编码规范合规

- 读取 `.agents/rules/coding-standards.md`
- 逐项检查：
  - [ ] 命名是否符合规范（camelCase / PascalCase / UPPER_SNAKE_CASE）
  - [ ] 注释是否解释了「为什么」
  - [ ] 函数是否标注了类型
  - [ ] 是否存在裸 `except`（Python）
  - [ ] 是否使用了 `console.log` / `print` 替代日志
  - [ ] 是否在 api 层直接操作了数据库

### 5. 输出报告

将检查结果整理为结构化报告：

```
## 代码质量报告

### 总览
- Lint 问题: X 个（Y 个已自动修复）
- 类型错误: X 个
- 安全问题: X 个
- 规范违规: X 个

### 详情
[按严重程度排列的问题列表]

### 建议
[改进建议]
```
