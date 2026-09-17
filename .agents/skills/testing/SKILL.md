---
name: testing
description: >-
  当用户要求编写测试、运行测试、TDD 开发、提高测试覆盖率、
  或进行测试分析时激活。支持单元测试、集成测试和端到端测试。
---

# 测试工作流

支持 TDD（测试驱动开发）和常规测试编写，确保代码质量和可靠性。

## 步骤

### 1. 确定测试范围

- 确认要测试的功能模块或代码变更
- 确定测试类型：
  - **单元测试**：独立函数和组件
  - **集成测试**：模块间交互
  - **端到端测试**：完整用户流程

### 2. TDD 模式（Red-Green-Refactor）

如果使用 TDD：

1. **Red**：先编写一个会失败的测试，明确预期行为
2. **Green**：编写最少量的代码使测试通过
3. **Refactor**：在测试保护下重构代码，保持测试通过

### 3. 编写测试

前端（Vitest + React Testing Library）：
```typescript
import { describe, it, expect } from 'vitest';
import { render, screen } from '@testing-library/react';

describe('ComponentName', () => {
  it('应该正确渲染', () => {
    render(<ComponentName />);
    expect(screen.getByText('expected text')).toBeInTheDocument();
  });
});
```

后端（pytest）：
```python
import pytest
from httpx import AsyncClient

@pytest.mark.asyncio
async def test_create_user(client: AsyncClient):
    """创建用户应返回 201 状态码"""
    response = await client.post("/api/users", json={"name": "test"})
    assert response.status_code == 201
```

### 4. 运行测试与覆盖率

```bash
# 前端
pnpm test                    # 运行所有测试
pnpm test -- --coverage      # 生成覆盖率报告

# 后端
pytest                       # 运行所有测试
pytest --cov=app --cov-report=html  # 生成覆盖率报告
```

### 5. 验证

- [ ] 所有测试通过
- [ ] 新增代码有对应的测试
- [ ] 覆盖率不低于当前基线
- [ ] 无跳过（skip）的测试未附带说明
- [ ] 测试命名清晰描述了预期行为
