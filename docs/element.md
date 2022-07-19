# 元素

## 图片和视频

* `object-fit`
  * `cover` 保持宽高比，某一条边顶边后裁剪。
  * `contain` 保持宽高比，某一条边顶边后，另一边留白。
  * `fill` 不保持宽高比，占满空间
  * `none` 图片尺寸不变，只展示图片的一部分或留白并居中。
  * `scale-down`: 如果图片比容器小，效果等于 `none`，否则等于 `contain`

替换元素拥有内在尺寸和默认基线，需要修改 `vertical-align` 对齐。

## 表格

* `table-layout` 表格布局
  * `auto` 自动根据容器调整每列宽度
  * `fixed` 保持设置的宽度
* `border-collapse`
  * `collapse` 单元格边框合并
  * `separate` 单元格边框分离
* `border-spacing` 单元格边框之间的距离
* `caption-side` 标题位置
  * `top`
  * `bottom`

## 表单

* `textarea, resize: auto`
* `appearance: none` 保留语义，去除元素默认样式

## 列表

* `list-style-type` 序号类型
* `list-style-position`
  * `inside`
  * `outside`
* `list-style-image`
* `list-style` 简写

### 控制有序列表的序号

* @counter-style
* counter-increment
* counter-reset

### 其它控制列表样式的方法

* 背景图
* 伪元素 `::marker` 配合 `content`
