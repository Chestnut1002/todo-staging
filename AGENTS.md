# toDoliSt（Win-Todo）项目开发指引

## 项目简介
toDoliSt 🌰 是一个纯网页待办事项应用，单文件 `index.html` 即开即用。基于原生 HTML/CSS/JS + localStorage，零依赖、零构建。帮助用户管理每日/每周/每月的目标任务。

## 标准文件路径

| 文档 | 路径 | 说明 |
|------|------|------|
| 需求文档 | [docs/requirements.md](docs/requirements.md) | 功能需求和非功能需求 |
| 技术规范 | [docs/tech.md](docs/tech.md) | 技术栈、架构、数据模型 |
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
- 使用对象字面量组织模块（`const App = { ... }`）
- 数据操作统一通过 `Storage` 对象，key 为 `todolist_local`
- CSS 使用 `--变量` 定义在 `:root` 中
- 动画使用 CSS transition/animation，避免 JS 动画
- 中文注释优先，清晰易懂

### 验证方式
- 双击 `index.html` 在浏览器中打开
- 检查浏览器控制台无报错
- 确认 UI 与 [docs/design.md](docs/design.md) 设计规范一致
