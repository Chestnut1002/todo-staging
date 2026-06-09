# 设计规范

## 颜色主题

| 用途 | CSS 变量 | 色值 |
|------|----------|------|
| 主背景 | `--bg-main` | `#f5f9ff` |
| 侧边栏背景 | `--bg-sidebar` | `#e8f1fc` |
| 主色调 | `--color-primary` | `#64b5f6` |
| 主色调 hover | `--color-primary-hover` | `#42a5f5` |
| 今天标记 | `--color-today` | `#1e88e5` |
| 文字主色 | `--text-primary` | `#333333` |
| 文字次要 | `--text-secondary` | `#888888` |
| 完成/禁用 | `--text-disabled` | `#bdbdbd` |
| 边框色 | `--border-color` | `#e0e0e0` |
| 白色 | `--white` | `#ffffff` |
| 危险/删除 | `--color-danger` | `#ef5350` |

## 字体

| 用途 | 规则 |
|------|------|
| 全局字体 | `system-ui, -apple-system, "Microsoft YaHei", sans-serif` |
| 标题 | `font-weight: 600` |
| 正文 | `font-weight: 400`, `font-size: 14px` |

## 间距

| 级别 | 值 |
|------|------|
| 基础单位 | 8px |
| 小间距 | 8px |
| 中间距 | 16px |
| 大间距 | 24px |

## 圆角

| 元素 | 值 |
|------|------|
| 按钮、输入框 | 8px |
| 卡片 | 12px |
| 月历格子 | 6px |

## 动画

| 用途 | 时长 | 缓动 |
|------|------|------|
| 任务删除渐隐 | 400ms | ease-out |
| 按钮 hover | 200ms | ease |
| 视图切换 | 250ms | ease |
| 搜索防抖 | 300ms | — |

## 布局规范

- 窗口默认尺寸：1000 x 680px
- 最小尺寸：800 x 500px
- 左侧月历宽度：280px
- 右侧任务区：自适应剩余宽度
- 搜索栏高度：40px
- 底部状态栏高度：36px

## 任务项样式

- 圆圈大小：20x20px，border 2px，未完成时空心、hover 时填充浅色
- 任务文字：14px，行高 1.5
- 标签（日期/周/月）：小圆角标签，10px 字号，淡蓝背景

## 月历样式

- 表头：周一至周日，12px 字号
- 日期格：36x36px 居中
- 今天：深蓝背景 + 白色文字
- 选中日期：中蓝边框
- 有任务标记：6px 小圆点，颜色 `--color-primary`
