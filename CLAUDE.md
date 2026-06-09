# Win-Todo 项目开发指引

## 项目简介
这是一个 Windows 桌面待办事项应用，基于 Electron + 原生 HTML/CSS/JS + sql.js 构建。帮助用户管理每日/每周/每月的目标任务。

## 标准文件路径

| 文档 | 路径 | 说明 |
|------|------|------|
| 需求文档 | [docs/requirements.md](docs/requirements.md) | 功能需求和非功能需求 |
| 技术规范 | [docs/tech.md](docs/tech.md) | 技术栈、架构、数据模型、IPC 设计 |
| 设计规范 | [docs/design.md](docs/design.md) | 颜色、字体、间距、动画、布局 |
| 执行步骤 | [docs/steps.md](docs/steps.md) | 开发步骤和进度追踪 |
| 开发日志 | [devlog/](devlog/) | 每日开发记录 |

## 工作说明

### 开发原则
1. **分步推进**：严格按照 `docs/steps.md` 中的步骤顺序开发，每一步完成并验证后再进入下一步
2. **先读规范**：修改任何代码前，先阅读对应的规范文档
3. **保持同步**：代码变更后同步更新 `docs/steps.md` 中的勾选状态
4. **每日日志**：每次开发会话结束后，在 `devlog/` 中更新日志文件（文件命名：`YYYY-MM-DD.md`）

### 开发流程
1. 阅读 `docs/requirements.md` 了解需求
2. 查阅 `docs/tech.md` 确认技术方案
3. 参考 `docs/design.md` 确保设计一致
4. 按 `docs/steps.md` 顺序执行
5. 完成后更新日志到 `devlog/YYYY-MM-DD.md`

### 代码风格
- 使用 CommonJS 模块（`require`）
- IPC 调用统一通过 `renderer/db.js` 封装
- CSS 使用 `--变量` 定义在 `:root` 中
- 动画使用 CSS transition/animation，避免 JS 动画
- 中文注释优先，清晰易懂

### 验证方式
- 每完成一个步骤，使用 `npm start` 启动应用验证
- 检查控制台无报错
- 确认 UI 与设计规范一致
