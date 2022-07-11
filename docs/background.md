# 背景和边框

* `background-color`: 颜色和透明度，取值见下一节
* `background-image`：背景图
  * 除了图片，也可以是渐变（见下方）。
  * 可以同时存在多张图，使用逗号分隔，此时 `repeat, size, position` 属性也需要写多个，如果数量不够会循环使用。
* `background-repeat`，控制背景图重复，默认自动平铺
  * `repeat`
  * `repeat-x`
  * `repeat-y`
  * `no-repeat`
* `background-size`，图片尺寸，可以是绝对值，也可以是百分比，还有两个枚举值
  * `cover`，覆盖整个元素，图片的一部分会超出元素而无法显示
  * `contain`，元素背景包含整个图片，顶边，可能会有留白。
* `background-position`，图片左上角相对元素左上角的位置。
  * 取值可以是数值和关键字，`top, bottom, left, right, center`
  * 两个值时，第一个表示水平，第二个表示垂直方向
  * 四个值时，根据方位和数字混搭，`top 20px right 10px` 表示距上 `20px`，距右 `10px`
* `background-attachment`
  * `scroll` 元素滚动时背景不变，页面滚动时变化
  * `fixed` 背景不变
  * `local` 背景变化
* `background-origin`
  * `border-box` 边框及内部都能看到背景
  * `padding-box` 内边距及内部都能看到背景
  * `content-box` 只有内容可以看到背景
* `background-clip`
  * `border-box` 边框及内部都能看到背景
  * `padding-box` 内边距及内部都能看到背景
  * `content-box` 只有内容可以看到背景
  * `text` 只有文字可以看到背景，文字颜色需要设为透明。
* `background` 背景简写，写尺寸必须先写位置，`size / position`

`background-origin` 与 `background-clip`的区别，`origin` 是修改定位基点，`clip` 是裁剪

## 渐变函数

### 线性渐变

重复线性渐变，linear-gradient

### 径向渐变

重复径向渐变。radial-gradient

### 边框

* 尺寸
* 颜色
* 样式
* 圆角

一个值指定四个角，
两个值时，第一个指定左上和右下，第二个指定右上和左下。
三个值时，第一个指定左上，第二个指定右上和左下，第三个指定右下
四个值时，第一个指定左上，顺时针，

可以通过 `border-top-right-radius` 指定右上角，
如果是两个值，第一个是水平，第二个是垂直。
