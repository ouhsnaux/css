# 取值

## 尺寸单位

* 百分比
* px
* em，根据父元素字体大小计算
* rem，格局根元素字体大小计算
* vw, vh，100vw等于浏览器宽度，100vh等于浏览器高度
* `calc()` 计算尺寸

## 颜色

* 关键字 `red, black` 等
* `#aabbcc`, `#aabbcc00`
* `rgb()`, `rgba()`
* `hsl()`, `hsla()`

## 角度单位

`1turn = 360deg = 2π rad = 400 grad`

## 百分比计算

`margin` 和 `padding` 的四个值都是根据父元素的宽度计算的，
可以使用 `width: 20%; height: 0; padding-bottom: 20%` 创建一个方形
