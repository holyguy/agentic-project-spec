---
name: documentation
description: >-
  当用户要求编写文档、更新文档、生成 API 文档、撰写 ADR、
  更新 CHANGELOG、更新 README、写架构文档时激活。
---

# 文档生成

根据文档类型执行不同的生成流程，确保项目文档完整、准确、可维护。

## 步骤

### 1. 确定文档类型

| 类型 | 目标文件 | 信息来源 |
|:-----|:---------|:---------|
| API 文档 | 自动生成（OpenAPI） | 代码中的路由和 Schema |
| 架构决策 | `docs/ADR/NNN-title.md` | 讨论记录、技术调研 |
| 变更日志 | `docs/CHANGELOG.md` | `git log` |
| 架构文档 | `docs/ARCHITECTURE.md` | 代码结构分析 |
| 领域模型 | `docs/CONTEXT.md` | 业务需求、代码实体 |
| README | `README.md` | 项目当前状态 |
| 路线图 | `docs/ROADMAP.md` | 需求规划 |

### 2. 收集信息

- **API 文档**：分析路由定义、请求/响应 Schema
- **ADR**：使用 `docs/ADR/000-template.md` 模板
- **CHANGELOG**：运行 `git log --oneline --since="上次发布"` 收集变更
- **架构文档**：分析目录结构和模块依赖关系

### 3. 生成文档

按照对应模板格式生成内容。ADR 编号规则：
```
NNN-简短描述.md
例如：001-use-fastapi.md
```

### 4. 更新索引

- 如果新增了 ADR，确认可以在 `docs/ADR/` 目录下找到
- 如果更新了架构，确认 `AGENTS.md` 中的指针仍然有效
- 如果项目有重大变更，更新 `STATUS.md`

### 5. 验证

- [ ] Markdown 格式正确，无语法错误
- [ ] 文档中的文件链接可访问
- [ ] 代码示例可执行
- [ ] 术语与 `docs/CONTEXT.md` 一致
