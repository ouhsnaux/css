# 盒模型

## 盒子分类

每个 `HTML` 元素默认属于块级盒子或行内盒子，可以使用 `display` 修改类型。

### 块级盒子

* 另起一行
* 可以设置宽高，自动占满父元素宽度
* 内外边距正常起作用

### 行内盒子

* 不另起一行
* 设置宽高无效，根据内容决定
* 水平方向边距可将元素推开，垂直方向边距不起作用（`<img>` 除外）

### 行内块级盒子

* 不另起一行
* 可设置宽高，否则根据内容决定
* 可设置内外边距

## 组成部分

* `content`，设置宽高，最小最大宽高
* `padding`，内边距
* `border`，边框
* `margin`，外边距

`padding/border/margin` 都有四个方向的属性，比如：

```css
.box {
  margin-top: 40px;
  margin-right: 30px;
  margin-bottom: 40px;
  margin-left: 30px;
}
```

`padding` 和 `content` 可以简写。根据值的个数，含义不同。

* 1个值，同时设置4个方向的属性
* 2个值，上下方向和左右方向
* 3个值，上方，左右，下方
* 4个值，顺时针，上右下左

### border

每条边框都包含3个属性

* `width` 宽度
* `style` 样式
  * `solid`
  * `dotted`
  * `dashed`
* `color` 颜色
* `border-radius`，根据值的个数，含义不同
  * 1个值，四个角
  * 2个值，第一个值是左上有右下
  * 3个值，左上，右上和左下，右下
  * 4个值，顺时针，左上，右上，右下，左下
* `border-image`

### margin

#### 外边距合并

当垂直方向的外边距直接接触时，会发生合并。

合并场景：

* 父子合并，父子元素同时存在外边距，父元素无内边距和边框
* 兄弟合并，一个元素的上边距和下一元素的上边距合并
* 自合并，一个元素没有高度、内边距和边框时，上下边距合并

合并后的值根据外边距正负，计算方式不同。

* 全是正值，取最大值
* 一正一负，求和
* 全是负值，取最小值

## 两种盒模型

* 标准盒模型：宽高等于 `content`。`box-sizing: content-box`
* 替补（IE）盒模型：宽高等于 `content + padding + border`。`box-sizing: border-box`

大部分情况下使用替补盒模型更方便。

## BFC

块级格式化上下文，创建一个独立布局的块。

### 作用

* 消除 `float` 子元素造成的高度塌陷
* 避免该元素与其直接子元素发生的 `margin` 合并

### 创建

* `flex, grid`
* 多列布局
* `float`
* `display: inline-block`
* `position` 为 `absolute, fixed`
* `overflow` 不为 `visible, clip`
* `display: flow-root`
* `contain`: `layout, content, paint`

## IFC

上面讲的行内盒子就是 `IFC`

## 溢出

盒子中内容过多就会发生溢出。

设置 `overflow` 修改溢出处理策略，`overflow-x` 和 `overflow-y` 分别处理水平和垂直方向的溢出。

* `visible` 可见，默认值，可能会与其它内容发生重叠
* `hidden` 隐藏溢出内容
* `scroll` 元素显示滚动条，可滚动查看溢出内容
* `auto` 只在需要时添加滚动条

当设置为 `scroll` 或者 `auto` 时会建立 `BFC`，盒子内外的布局互不影响。

## 其他

* `aspect-ratio` 宽高比
* `outline`，在 `border` 外部，不占据空间，
  * `outline-width`
  * `outline-style`
  * `outline-color`
  * `outline-offset` 距边框的距离
* `box-shadow`
  * 水平偏移
  * 垂直偏移
  * 模糊半径
  * 传播半径
  * inset 是否内部阴影
  * 颜色
