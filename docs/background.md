# 背景

## 属性

* `background-color`: 背景色
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

### 线性渐变 `linear-gradient`

* 方向，默认 `to bottom`
  * 关键字，`to top, to bottom, to left top`
  * 角度，渐变线按顺时针旋转
    * `0deg` 时从下往上
    * `90deg` 时从左往右
  * 渐变区域，从元素的4个基点向渐变线做垂线和平行线，围成的长方形与元素的交集
* 节点
  * 多个节点用逗号分隔
  * 每个节点包括颜色和位置
    * 位置可用长度或百分比，默认放置在前后节点的中间位置
    * 每个节点也可以包含两个位置，相当于两个相同颜色的节点合并，此时也可以拆成两个节点，第二个节点不写颜色
    * 自动添加起止点，颜色默认与相邻节点相同

### 径向渐变 `radial-gradient`

* 第一个参数包含三部分
  * 形状
    * `circle`
    * `ellipse`，默认是此值
  * 中心点，默认最中间
    * `at` 开头
    * 第一个值指定水平方向的位置，第二个指定垂直方向的位置
  * 终点，默认是最远角
    * `farthest-corner` 最远的角
    * `farthest-side` 最远的边
    * `closest-corner` 最近的角
    * `closest-side` 最近的边
* 节点，同线性渐变

### 锥形渐变 `conic-gradient`

* 第一个参数包含两部分
  * 起始角度 `from + 角度`
  * 中心点，默认最中间
    * `at` 开头
    * 第一个值指定水平方向的位置，第二个指定垂直方向的位置
* 节点
  * 位置使用角度，其它同径向渐变

可以用来实现饼图，象棋棋盘

### 重复渐变

`repeat-linear-gradient, repeat-radial-gradient, repeat-conic-gradient` 不会自动添加终点，从结束节点自动重复渐变。最后一个节点位置默认 `100%`。如果起点与终点颜色相同，则终点到起点之间也是渐变色。否则终点到起点之间颜色会突变。
