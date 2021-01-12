# 过渡

## 作用

在 `CSS3` 中，当从一种样式转变为另一种的时候，产生过渡效果，
以免显得突兀。

## 使用

### 过渡属性 `transition`

* `transition-property` - 应用过渡的css属性
* `transition-duration` - 过渡花费的时间
* `transition-timing-function` - 过渡效果的时间曲线
* `transition` - 以上三种属性的简写
* `transition-delay` - 延迟执行

### 转换属性 `transform`

与过渡配合产生动画。

* `transform` - 转换，有5种转换方式。
* `transform-origin` - 转换基点，比如旋转围绕的原点。
* `transform-style` - 转换类型，分为 `2d` 和 `3d`。
* `perspective` 元素与视图的距离，放到父元素才起作用。

### 转换方式

* `translate` - 移动，参数为距离
* `rotate` - 旋转，参数为角度
* `scale` - 缩放，参数为倍数
* `skew` - 拉伸，参数为角度
* `matrix` - 一个方法可实现以上四种功能

`translate`、`scale` 和 `skew` 都有两个参数，
分别表示x轴和y轴的形变程度，
同时每个方法还有两个类似的方法，比如
`translateX`，沿x轴移动，
`translateY`，沿y轴移动。

`matrix` 有6个参数，可实现所有功能。

### transform-origin

转换的基点，对 `rotate`、`scale` 和 `skew` 起作用。

### 3d转换

`css3` 除了能做 `2d` 转换外，还可以实现 `3d` 转换效果
