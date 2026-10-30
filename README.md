# lolitacoding.github.io

Lolitacoding 的官网，托管在 GitHub Pages：<https://lolitacoding.github.io/>。

单页、手写 HTML/CSS，没有构建步骤、没有框架、没有外部字体或 CDN。改完直接推送，
Pages 从 `main` 根目录发布，一两分钟后线上就更新了。

## 结构

| 文件 | 作用 |
| --- | --- |
| `index.html` | 整站内容：定位、特性、版本对照、代码示例、包列表、快速开始、文档入口。 |
| `assets/styles.css` | 全部样式，含响应式断点、`prefers-reduced-motion` 和打印样式。 |
| `assets/main.js` | 代码标签页（含方向键切换）与复制按钮；禁用 JS 时所有面板仍然可见。 |
| `assets/favicon.svg` | 站点图标，也是页头的品牌标记。 |
| `404.html` | GitHub Pages 的自定义 404。 |
| `robots.txt` / `sitemap.xml` | 搜索引擎用。 |
| `.nojekyll` | 跳过 Jekyll，静态文件原样发布。 |

## 本地预览

不需要装任何东西，用任意静态服务器打开仓库根目录即可：

```bash
python -m http.server 8080
# 然后访问 http://localhost:8080/
```

直接双击 `index.html` 也能看，只是复制按钮在 `file://` 下可能被浏览器禁用。

## 发布

Pages 设置：**Source: Deploy from a branch → `main` → `/ (root)`**。
没有 Actions 工作流，所以每次推送都是零构建、零分钟数。

## 改内容时注意

- 页面上的版本对照表来自 `docs/faq.md` 与 `docs/releasing.md`，Nacos 支持范围变了要同步。
- 代码示例必须能编译：它们是从 README 与 `docs/quickstart.md` 抄来的，改了 API 记得一起改。
- 数字（单元测试 924、集成测试 64）会随仓库变化，发版前顺手更新。
- 源码仓库 `Lolitacoding.Nacos` 目前是私有的，页面上的 GitHub 链接要等仓库公开后才可用。
