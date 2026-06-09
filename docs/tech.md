# 技术规范

## 技术栈

| 层 | 技术 | 说明 |
|---|------|------|
| 平台 | 纯网页（浏览器） | 双击 index.html 即用，无需安装 |
| 前端 | 原生 HTML + CSS + JavaScript | 单文件，无框架，零依赖 |
| 存储 | localStorage | 浏览器本地存储，数据持久化 |
| 运行 | 任意现代浏览器 | Chrome / Edge / Firefox 均可 |

## 项目结构

```
win-todo/
├── index.html               # 主应用（单文件，包含全部 HTML/CSS/JS）
├── CLAUDE.md                # AI 助手指引
├── docs/                    # 项目规范文档
│   ├── requirements.md      # 需求文档
│   ├── tech.md              # 技术规范（本文件）
│   ├── design.md            # 设计规范
│   └── steps.md             # 执行步骤
├── devlog/                  # 开发日志
│   ├── 2026-06-09.md
│   └── 2026-06-10.md
├── assets/                  # 静态资源
├── renderer/                # Electron 版源码（已弃用，保留参考）
│   ├── index.html
│   ├── styles.css
│   ├── app.js
│   ├── calendar.js
│   ├── task-list.js
│   ├── search.js
│   └── db.js
├── main.js                  # Electron 主进程（已弃用）
├── preload.js               # Electron 预加载（已弃用）
├── package.json             # Electron 依赖配置（已弃用）
└── electron-builder.yml     # Electron 打包配置（已弃用）
```

## 架构设计

### 单文件架构
- 所有 HTML、CSS、JS 内嵌在 `index.html` 中
- 无需服务器、无需构建、双击即可运行
- 代码按模块划分在 `<script>` 内：
  - **Storage** — localStorage CRUD 封装
  - **Calendar** — 月历组件
  - **TaskList** — 任务列表 + 渐隐动画
  - **Search** — 搜索功能
  - **App** — 主逻辑 + 视图切换

### 数据存储
- 使用 `localStorage`，key 为 `win-todo-tasks`
- 数据格式：JSON 数组
- 每个任务对象结构：

```js
{
  id: number,           // 时间戳生成唯一 ID
  title: string,        // 任务名称
  date: string | null,  // 具体日期 YYYY-MM-DD
  periodType: string,   // 'day' | 'week' | 'month'
  periodValue: string,  // 周期标识，如 '2026-W24' 或 '2026-06'
  completed: 0 | 1,     // 0=未完成 1=已完成
  createdAt: string     // ISO 时间戳
}
```

## 代码规范
- 使用对象字面量组织模块（`const App = { ... }`）
- CSS 使用 CSS 变量定义主题色
- 所有 UI 交互优先使用 CSS transition/animation
- 数据操作统一通过 `Storage` 对象
