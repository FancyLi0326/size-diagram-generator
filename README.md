# 尺寸图生成器

这是一个单页 Three.js 工具，用于生成商品尺寸参考图。工具可以直接在本地浏览器打开，不需要安装依赖或启动服务。

## 如何打开

双击 `index.html` 即可使用。也可以在浏览器中打开本地文件：

`C:\Users\LFX\Documents\尺寸\size-diagram-generator\index.html`

## 文件结构

```text
size-diagram-generator/
  index.html              核心页面和全部交互逻辑
  README.md               使用说明
  HANDOFF.md              项目交接说明
  CODEX_HANDOFF.md        给 Codex 继续开发的交接说明
  assets/                 图片资源
  vendor/three.min.js     本地 Three.js 依赖
```

## 当前功能

- 支持 `地面放置` 和 `桌面放置` 两种布局。
- 可调整立方体宽、高、深、宽高比和锁定比例。
- 可控制是否带凹槽、间距、底部虚线范围等特殊效果。
- 支持 3:2、4:3、16:9 三种输出比例。
- 支持视图镜距、透视、水平角、垂直角和画面平移。
- 支持双击画布文字直接编辑、拖拽移动、删除文字和调整字号。
- 支持 6 个方案槽位，点击“保存”后写入缩略图。
- 支持导出当前画面，以及批量导出全部已保存方案。
- 会自动保存本地工作区，下次打开可恢复上次状态。

## 使用建议

1. 先选择布局和输出比例。
2. 调整立方体尺寸、凹槽和标注线位置。
3. 用右侧工具微调视图和文字。
4. 满意后点击方案槽里的“保存”。
5. 需要单张图片时点“导出当前”，需要多个方案时点“导出全部”。

## 继续开发提示

- 不要从头重做，核心代码都在 `index.html`。
- 修改桌面布局优先看 `applyLayoutPreset("tabletop")` 和 `addTabletopScene()`。
- 修改显示/隐藏控件优先看 `syncControlVisibility()`。
- 修改颜色同步优先看 `syncSceneColorMaterials()`。
- 修改导出逻辑优先看 `createCompositeCanvas()`、`downloadCanvas()`、`exportCurrentView()`、`exportAllVariants()`。
