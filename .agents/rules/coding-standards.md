# 编码规范

本文件包含项目的详细编码规范，由 AGENTS.md 引用，按需加载。

## 命名规范

| 类型 | 风格 | 示例 |
|:-----|:-----|:-----|
| 变量 / 函数 | camelCase | `getUserName` |
| 类 / 组件 | PascalCase | `UserCard` |
| 常量 | UPPER_SNAKE_CASE | `MAX_RETRY_COUNT` |
| 文件 / 文件夹 | kebab-case | `user-profile.tsx` |
| 环境变量 | UPPER_SNAKE_CASE | `DATABASE_URL` |
| CSS 类名 | kebab-case 或 BEM | `user-card__title` |

> 命名应语义清晰，禁止随意缩写。

## 注释规范

### 原则
- 注释用于解释「为什么这样设计」，而不是代码字面含义
- 复杂逻辑、业务判断、边界条件必须写注释
- 禁止无意义注释（如 `// 设置变量`）

### 标记约定

```text
// TODO  : 待实现功能
// FIXME : 已知问题或潜在缺陷
// NOTE  : 重要设计说明
// HACK  : 临时方案，后续必须重构
```

### 函数注释

前端（JSDoc）：
```ts
/**
 * 获取用户信息
 * @param userId 用户 ID
 * @returns 用户数据
 */
```

后端（Python Docstring）：
```python
def get_user(user_id: str) -> User:
    """
    根据用户 ID 获取用户信息

    Args:
        user_id: 用户唯一标识

    Returns:
        用户数据对象

    Raises:
        UserNotFoundError: 用户不存在时抛出
    """
```

## 前端规范（React + TypeScript）

### 基本原则
- 使用函数组件，不使用类组件
- 单个组件只承担单一职责
- 展示逻辑与业务逻辑分离
- 可复用逻辑必须抽离为自定义 Hook

### 组件命名
- 组件名使用 PascalCase
- 文件名与组件名保持一致（kebab-case 文件名）
- 自定义 Hook 必须以 `use` 开头

### Props 规范
- 必须使用 TypeScript interface 定义
- 使用解构方式接收 props
- 非必传参数使用 `?`

```ts
interface UserCardProps {
  user: User;
  onClick?: () => void;
}
```

### Hooks 使用规范
- 只能在函数组件或自定义 Hook 中调用
- 不允许在条件、循环中调用
- 一个 Hook 只处理一种职责

### 性能要求
- 避免不必要的重复渲染
- 合理使用 `useMemo` / `useCallback`
- 列表渲染必须提供稳定的 `key`
- 大数据列表使用虚拟滚动
- 路由与组件支持懒加载

## 后端规范（Python）

### 基本要求
- Python ≥ 3.10
- 优先使用 FastAPI
- 所有函数与方法必须标注类型
- 禁止使用裸 `except`
- 禁止使用 `print` 作为日志方式，使用 `logging` 模块

### 分层结构

| 层级 | 职责 | 示例文件 |
|:-----|:-----|:---------|
| api | 请求解析与响应封装 | `api/user_router.py` |
| service | 业务逻辑处理 | `service/user_service.py` |
| repository | 数据库访问 | `repository/user_repo.py` |
| schema | 请求/响应数据校验 | `schema/user_schema.py` |
| model | ORM 模型定义 | `model/user.py` |

> 禁止在 api 层直接操作数据库。

### 日志规范
- 使用 `logging` 模块
- 合理区分日志级别：DEBUG / INFO / WARNING / ERROR
- 日志中不得包含敏感信息（密码、Token、身份证号等）

## 安全规范

### 前端安全
- 禁止使用 `dangerouslySetInnerHTML`
- 防止 XSS / CSRF 攻击
- 不在前端存储敏感信息
- Token 推荐使用 HttpOnly Cookie

### 后端安全
- 使用 Pydantic 进行参数校验
- 权限校验必须在 service 层完成
- 所有密钥从环境变量中读取
- 敏感字段返回前需脱敏
- 密码等敏感数据必须加密存储

## Git 提交规范

使用 Conventional Commits 格式：

```
<type>(<scope>): <description>

[body]

[footer]
```

类型：
- `feat`: 新功能
- `fix`: 修复 Bug
- `docs`: 文档变更
- `style`: 代码格式（不影响功能）
- `refactor`: 重构
- `test`: 测试相关
- `chore`: 构建/工具变更
