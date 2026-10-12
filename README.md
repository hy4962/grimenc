# HY-图片混淆

在线图片混淆 / 解混淆工具。纯前端运行，图片全程留在本地浏览器，不上传任何服务器。

- 线上地址：<https://hunxi.9ll.uk/>
- 博客：<https://www.9ll.uk/>

---

## 功能

- 混淆 / 解混淆，支持连续多次叠加
- 混淆强度、解混淆强度各 5 档：`0.0 / 0.5 / 1.0 / 1.5 / 2.0`
- 绿图增强（提升绿色 80%）、减弱绿色效果
- 输出 PNG（无损）或 JPG（有损，质量可调）
- 分块迭代处理，秒级加载
- 下载、查看、清除图片，随时还原原图
- 深色 / 浅色主题，跟随系统并可手动切换

## 界面

界面由 HY 按 9LL.UK 博客（Firefly 主题）的风格重构：

- 同一套 OKLCH 色板与 `--hue: 65` 暖琥珀强调色
- 同一套圆角 / 阴影 / 模糊令牌（`--radius-*`、`--shadow-*`、`--blur-*`）
- 自托管字体子集，与博客同源：Inter、Zen Maru Gothic、JetBrains Mono（见 `fonts/`）

## 说明

混淆 / 解混淆算法逻辑来自上游项目 [Gascy37/grimenc](https://github.com/Gascy37/grimenc)（MIT），
本次只重做前端样式与少量界面脚本，算法部分未改动。原始版权声明见 [LICENSE.md](LICENSE.md)。

## 部署

纯静态站点，`wrangler.jsonc` 已声明 `assets.directory` 为仓库根目录，直接用 Cloudflare Workers 静态资源部署即可。

```bash
npx wrangler deploy
```

本地预览任意静态服务器均可：

```bash
python -m http.server 8123
```
