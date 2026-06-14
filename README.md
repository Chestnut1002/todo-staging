# toDoliSt 🌰

> 一个简洁、可爱的待办事项应用 —— 双击 `index.html` 即用，无需安装。
> A simple, cute todo app — double-click `index.html` and go. No install needed.

---

## 在线试用 Live Demo

🔗 [chestnut1002.github.io/todo-staging/](https://chestnut1002.github.io/todo-staging/)



## 功能特性 Features

### 📋 任务管理 Task Management
- ✅ 添加、完成、删除任务（渐隐动画）
- ✅ Add, complete (fade-out animation), and delete tasks

### 📅 三种视图 Three View Modes
- 📆 **日视图** — 查看某一天的任务
- 📊 **周视图** — 查看本周所有任务
- 🗓️ **月视图** — 查看本月所有任务

### 📆 月历组件 Calendar Widget
- 月份切换（左右箭头）
- 今日日期高亮
- 有任务的日期显示小圆点标记
- 点击日期可快速跳转

### 🔍 模糊搜索 Fuzzy Search
- 输入即搜，300ms 防抖
- 任务名称模糊匹配
- 关键字高亮显示
- ESC 或点击清除按钮退出搜索

### 🎯 三级优先级 Priority Levels
- 🔴 重要 / High
- 🟡 一般 / Medium  
- ⚪ 不强制 / Low

### 📌 截止日期 Deadline
- 为任务设置截止时间
- 倒计时标签自动变色：蓝（充裕）→ 橙（临近）→ 红（过期）

### ↕️ 拖拽排序 Drag & Drop
- 鼠标拖拽调整任务顺序
- 支持触屏设备

### 📊 进度统计 Progress Stats
- 底部状态栏显示任务总数和完成数
- 进度条直观展示完成率

### 🔔 浏览器通知 Notifications
- 截止日期临近自动推送浏览器通知
- 每 10 分钟检查一次

### 📱 响应式布局 Responsive
- 桌面端双栏布局（日历侧栏 + 任务列表）
- 移动端自适应单栏布局

### 🚀 PWA 支持 PWA Support
- Service Worker 离线缓存
- 可添加到手机/桌面主屏幕
- 离线也能使用

---

## 如何使用 How to Use

### 方法一：直接打开（最简单）
1. 下载 `index.html`
2. 双击在浏览器中打开
3. 开始管理你的任务！

### 方法二：本地服务器（PWA / 通知功能需要）
```bash
# 使用 Python
python -m http.server 8080

# 或使用 Node.js
npx serve .
```
然后打开 `http://localhost:8080`

### 方法三：部署到 GitHub Pages
1. Fork 本仓库
2. Settings → Pages → Source: GitHub Actions（推荐）或直接选分支
3. 保存，等待部署完成

---

## 技术栈 Tech Stack

| 层级 | 技术 | 说明 |
|------|------|------|
| 前端 | 原生 HTML + CSS + JavaScript | 零框架、零依赖 |
| 存储 | localStorage | 浏览器本地持久化 |
| 离线 | Service Worker | PWA 离线缓存 |
| 通知 | Notification API | 浏览器原生通知 |
| 部署 | GitHub Pages | 静态站点托管 |

**核心亮点：** 整个应用只有 **一个 `index.html` 文件**，无需 `npm install`，无需构建工具，在任何现代浏览器中直接运行。

---

## 项目结构 Project Structure

```
win-todo/
├── index.html               # 主应用（单文件，全部 HTML/CSS/JS）
├── README.md                # 项目说明
├── LICENSE                  # MIT 协议
├── CLAUDE.md                # 开发指引
├── docs/                    # 规范文档
│   ├── requirements.md      # 需求文档
│   ├── tech.md              # 技术规范
│   ├── design.md            # 设计规范
│   ├── steps.md             # 开发步骤
│   └── bugs.md              # 缺陷报告（测试实践）
├── test/                    # 测试用例
│   └── test-cases.md        # 45 条测试用例
└── devlog/                  # 开发日志
    ├── 2026-06-09.md
    └── 2026-06-10.md
```

---

## 测试文档 Testing

本项目包含完整的测试实践文档，展示软件测试全流程能力：

- 📋 **[45 条测试用例](test/test-cases.md)** — 覆盖 9 大模块，采用等价类划分、边界值分析、场景法设计
- 🐛 **[缺陷报告](docs/bugs.md)** — 含复现步骤、根因分析、修复方案、回归测试记录
- 📊 测试覆盖率统计 — 功能测试 · 兼容性测试（Chrome/Edge/Firefox/移动端）· 数据持久化测试

---

## 开发故事 Development Story

这个项目最初计划做成一个 **Electron 桌面应用**，使用 sql.js（SQLite 编译到 WebAssembly）做本地数据库，打包成 Windows `.exe` 安装包。

但在 Windows 上遇到了 Electron 37 的模块解析问题——`require('electron')` 无法正常返回 API。经过排查和尝试后，决定做一个果断的架构决策：

> **放弃 Electron，转为纯网页单文件方案。**

这个决策带来了意外的好处：
- 🎯 零依赖，没有 `node_modules` 负担
- 🚀 零构建，修改即刷新
- 📦 一个文件，拷到哪都能用
- 🌐 天然跨平台（Windows / Mac / Linux / 手机）

在 v2 版本中，又陆续加入了优先级、截止日期、拖拽排序、PWA、浏览器通知等功能，让这个"简单"的待办事项应用变得实用而完整。

---

## 致谢 Credits

Made with 🌰 by [@chestnut1002](https://github.com/chestnut1002), 2026

---

## 开源协议 License

MIT © 2026 — 自由使用、修改、分发。
