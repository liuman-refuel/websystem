# public 目录说明

此目录下的文件在构建时会**原样复制**到打包产物的根目录（`dist/`），且**不参与哈希命名**。

## 适用场景

- **favicon.ico**：浏览器标签页图标，需固定路径 `/favicon.ico`
- **站点图标、PWA 图标**：如 `apple-touch-icon.png`、各类尺寸的 icon
- **无需打包处理的静态资源**：如 `robots.txt`、`sitemap.xml`

## 使用方式

1. 将文件放入本目录，例如：
   - `favicon.ico`
   - `logo.png`
   - `icons/xxx.ico`

2. 在代码或 HTML 中通过**根路径**引用：
   - HTML：`<link rel="icon" href="/favicon.ico" />`
   - 图片：`<img src="/logo.png" />`
   - 路径以 `/` 开头，对应部署后的网站根路径

## 与 src/assets 的区别

| 位置        | 引用方式           | 构建行为           | 适用场景           |
| ----------- | ------------------ | ------------------ | ------------------ |
| **public/** | 绝对路径 `/xxx`    | 原样复制，不改名   | favicon、固定路径  |
| **src/assets/** | `@/assets/xxx` 或 import | 参与打包，可哈希 | 组件内图片、需打包 |
