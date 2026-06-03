# 尺寸图生成器

这是一个单文件 Three.js 工具，用于生成带真实透视关系的尺寸图。

## 文件结构

```text
size-diagram-generator/
  index.html
  README.md
  vendor/
    three.min.js
```

## 如何打开

直接双击 `index.html` 即可在浏览器里打开。
项目使用普通脚本版 Three.js，不依赖 ES module，本地 `file://` 打开也可以渲染。

## 当前功能

- 左侧调整器，右侧预览。
- 可调宽、高、深、间距。
- 可调相机镜距和水平角，透视由 Three.js `PerspectiveCamera` 真实渲染。
- 可显示/隐藏右侧凹槽。
- 主体默认为立方体。
- 右侧凹槽默认略大于主体，并和主体共享同一组尺寸参数。

## 后续开发方向

- 增加导出图片功能。
- 增加保存/加载参数功能。
