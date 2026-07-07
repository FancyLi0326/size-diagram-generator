# 家群尺码生成器 Codex 交接说明

## 项目背景

这个项目用于生成标准化商品尺寸参考图。设计侧可以为不同品类、不同 SKU 比例输出统一参考图，研发据此生成比例准确、布局一致的最终尺码图。

当前项目已经是可用的单页工具。用户希望后续继续小步完善，不要从头重做，也不要大范围重构。

## 当前本地项目

- 本地目录：`C:\Users\LFX\Documents\尺寸\size-diagram-generator`
- 主文件：`index.html`
- 本地依赖：`vendor/three.min.js`
- 说明文档：`README.md`
- Codex 继续开发交接：`CODEX_HANDOFF.md`
- 可直接打开：双击 `index.html`

## 交接与分享方式

- 给同事继续开发时，请发送整个 `size-diagram-generator` 文件夹或 zip 包，不要只发送 `index.html`。
- 对方解压后，进入文件夹并双击 `index.html` 即可使用。
- Three.js 依赖在 `vendor/three.min.js`，不要删除。
- 如果需要发给研发作为参考工具，建议同时附上 `HANDOFF.md` 和 `README.md`。
- 如果只是给别人使用在线版本，可以直接发 GitHub Pages 链接。

## GitHub 发布

- 仓库：https://github.com/liuzhaoran88-rgb/jiaqun-size-diagram-generator
- Pages：https://liuzhaoran88-rgb.github.io/jiaqun-size-diagram-generator/

## 已实现功能

- 地面放置：立方体与右侧凹槽的尺寸参考图。
- 桌面放置：适合桌面安装、桌面放置类品类。
- 桌面放置支持有凹槽 / 无凹槽切换。
- 凹槽尺寸默认略大于立方体。
- 支持标注线位置：自动、样式1、样式2。
- 相机支持镜距、透视、水平角、垂直角和上下左右平移。
- 鼠标中键可拖拽移动画面。
- 背景立面支持白色 / 灰色。
- 墙线支持显示 / 隐藏。
- 文字可在画布中双击编辑，支持删除、移动和字号选择。
- 支持 6 个方案槽位，用户点击“保存”后才写入缩略图。
- 支持导出当前画面、导出全部已保存方案。
- 会自动保存本地工作区，下次打开可恢复上次状态。

## 最近调整重点

- 默认主体固定为立方体，不再生成商品白膜或品类模型。
- 颜色设置已简化，标注线、轮廓线和商品侧面颜色改为固定规则。
- 特殊效果已收拢到折叠区域，减少界面拥挤。
- 桌面模式下墙线粗细按布局即时切换。
- 桌面模式下“间距”控制立方体离桌面的悬浮距离。
- 桌面模式去掉投影。
- 文本输入框已取消，文字改为直接在画布上编辑。
- “导出当前”现在导出当前画面，不再依赖当前方案槽是否已保存。

## 继续开发建议

- 若继续微调标注线位置，重点修改 `addTabletopScene()` 或对应地面布局中的 `addDimension(...)`。
- 若继续调整默认桌面布局，重点修改 `applyLayoutPreset("tabletop")` 中的 `height`、`gap`、`cameraPitch` 等参数。
- 若继续调整控件显隐，重点修改 `syncControlVisibility()`。
- 若继续调整保存和导出，重点修改 `saveVariant()`、`exportCurrentView()`、`exportAllVariants()`。
- 修改后建议至少检查一次脚本语法，并在浏览器中打开页面确认效果。
