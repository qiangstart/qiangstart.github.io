---
title: 三步给网站加上深色模式
date: 2026-10-20 20:30:00
categories: 前端
tags: [CSS, 深色模式]
description: 用 CSS 变量 + prefers-color-scheme + 一点 JavaScript，就能实现可切换的深色模式。
---

深色模式已经是现代网站的标配，实现起来其实非常简单。

## 1. 用 CSS 变量定义颜色

```css
:root {
  --bg: #ffffff;
  --text: #1f2328;
}
body {
  background: var(--bg);
  color: var(--text);
}
```

## 2. 跟随系统设置

```css
@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0d1117;
    --text: #e6edf3;
  }
}
```

## 3. 允许手动切换

```js
const toggle = () => {
  const root = document.documentElement
  const next = root.dataset.theme === 'dark' ? 'light' : 'dark'
  root.dataset.theme = next
  localStorage.setItem('theme', next)
}
```

{% note warning flat %}
记得在 `<head>` 里尽早读取 `localStorage` 并设置主题，否则页面加载时会闪一下白屏。
{% endnote %}

本博客右下角的按钮就是深色模式开关，点一下试试吧 🌙
