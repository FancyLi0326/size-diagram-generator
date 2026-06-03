# 家群尺码生成器 Codex 交接说明

## 项目背景

这个项目用于约束研发生成标准化的商品尺码图。设计侧需要为不同品类、不同 SKU 比例输出标准参考图，研发据此生成比例准确、布局一致的最终尺码图。

当前已基于 vibe coding 搭建生成器雏形。工具通过选择布局、调整商品宽高深比例、凹槽关系、相机视角、标注颜色等参数，快速生成并导出不同比例主体的标准参考图。

## 当前本地项目

- 本地目录：`/Users/liuzhaoran/size-diagram-generator`
- 主文件：`index.html`
- 本地依赖：`vendor/three.min.js`
- 资源图：`assets/fridge-front-sku.png`、`assets/fridge-side-texture-a.png`
- 可直接打开：双击 `index.html`，或在浏览器访问 `file:///Users/liuzhaoran/size-diagram-generator/index.html`

## 交接与分享方式

- 给同事继续开发时，请发送整个 zip 包，不要只发送 `index.html`。
- 对方解压后，进入 `size-diagram-generator/` 文件夹，双击 `index.html` 即可看到尺寸图生成器。
- 如果对方要进一步修改，核心代码都在 `index.html` 中；Three.js 依赖在 `vendor/three.min.js`，不要删除。
- 如果对方再把工具发给别人，也请继续发送整个文件夹或整个 zip 包。
- 如果只是给别人使用在线版本，可以直接发 GitHub Pages 链接。
- 如果需要发给研发作为参考工具，建议同时附上 `HANDOFF.md`，方便理解工具背景和后续可扩展方向。

## GitHub 发布

- 仓库：https://github.com/liuzhaoran88-rgb/jiaqun-size-diagram-generator
- Pages：https://liuzhaoran88-rgb.github.io/jiaqun-size-diagram-generator/

说明：本机系统自带 `git` 当前不可用，报 Xcode 相关错误；此前发布是通过 GitHub CLI/API 上传完成的。

## 已实现功能

- 地面放置：立方体与右侧凹槽的尺寸参考图。
- 桌面放置：适合桌面安装、放置类品类。
- 桌面放置支持有凹槽 / 无凹槽切换。
- 凹槽尺寸默认略大于立方体。
- 相机支持镜距、角度、上下平移。
- 颜色设置支持调整标注线、墙线、轮廓线、商品侧面、凹槽底色。
- 支持 6 个方案槽位，用户点击“保存”后才写入缩略图。
- 支持导出当前方案、导出全部已保存方案。
- 切换布局时会清空方案缩略图，因为不同布局不共用方案。

## 最近调整重点

- 默认主体固定为立方体，不再生成商品白膜或品类模型。
- 桌面放置默认立方体更矮，悬浮间距更高。
- 桌面凹槽高度已与立方体高度联动，立方体变矮时凹槽同步变浅。
- 桌面模式下“间距”控制立方体离桌面的悬浮距离，不再与高度绑定。
- 桌面模式去掉投影。
- 桌面模式底部凹槽横向标注线已尽量贴近凹槽前侧灰线。
- 左侧凹槽深度标注线改为贴合桌面开口左边缘。

## 继续开发建议

- 若继续微调标注线位置，重点修改 `addTabletopScene()` 中末尾几条 `addDimension(...)`。
- 若继续调整默认桌面布局，重点修改 `applyLayoutPreset("tabletop")` 中的 `height`、`gap`、`cameraPitch`。
- 若要重新发布到 GitHub Pages，可继续使用 GitHub CLI；注意本机 `git` 可能需要先修复 Xcode Command Line Tools。
