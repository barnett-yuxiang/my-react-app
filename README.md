# React + TypeScript + Vite + Tailwind CSS 项目配置指南

本文档记录了配置 React + TypeScript + Vite + Tailwind CSS 开发环境的关键步骤。

## 创建项目

首先创建一个基于 Vite 的 React TypeScript 项目：

```bash
npm create vite@latest my-react-app -- --template react-ts
cd my-react-app
```

## 安装 Tailwind CSS

安装 Tailwind CSS 及其依赖：

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

> 注意：`npx tailwindcss init -p` 会自动创建 `postcss.config.js` 和 `tailwind.config.js` 文件，无需手动创建。这里会失败，还是要手动创建。

## 配置 Tailwind CSS

编辑 `tailwind.config.js` 文件：

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## 更新 CSS 文件

在 `src/index.css` 中添加 Tailwind 指令：

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 模块类型说明

项目中 `package.json` 的 `"type": "module"` 配置指定使用 ES 模块系统。

如需使用 CommonJS 格式，可以：
- 删除 `"type": "module"` 配置
- 或将配置文件扩展名改为 `.cjs`（例如 `tailwind.config.cjs`）

## 启动开发服务器

```bash
npm run dev
```
