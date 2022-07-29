# 动画与过渡

## transform

### 函数

书写顺序：

1. perspective
2. scale
3. translate
4. rotate

#### 平移

* `translate(x, y)`
* `translateX, translateY, translateZ`
* `translate3d(x, y, z)`

#### 旋转

* `rotate` 等于 `rotateZ`
* `rotateX, rotateY, rotateX`
* `rotate3d(x, y, z)`
* 坐标轴会跟着旋转

#### 倾斜

* `skew(x, y)`
* `skewX, skewY`

#### 缩放

* `scale(x, y)`
* `scaleX, scaleY, scaleZ`
* `scale3d(x, y, z)`

#### 形变

* `matrix` 自定义形变
* `matrix3d()`

### perspective

* `perspective` 定义屏幕到z=0平面的距离，默认无限远的距离
* `perspective-origin` 基点

### 其它

* `backface-visibility` 3d下背面的元素是否可见，背景色需透明
  * `visible` 默认
  * `hidden`
* `transform-style`
  * `flat` 平面，子元素一直在父元素上方
  * `preserve-3d` 3d形式，z坐标小的面会被父元素遮挡
* `transform-origin` 形变的基点
* `transform-box` `transform-origin` 基点
  * `content-box`
  * `border-box`

## transition

当一个元素的样式发生变化时，使用 `transition` 添加过渡效果，自动补齐中间过程。

* `transition-property` 过渡属性
  * `none`
  * `all`
  * 其它
* `transition-duration` 时长
* `transition-delay` 延迟，可以为负数
* `transition-timing-function` 过渡时间函数
  * `linear` 匀速
  * `ease, ease-in, ease-out, ease-in-out`
  * `cubic-bezier`
  * `steps` 步进
* `transition` 简写 `property duration function delay`

高度为 `auto` 时不能产生过渡效果。

可以同时设置多个过渡，使用逗号分隔。

## animation

### 使用动画

* `animation-name`
* `animation-duration`
* `animation-timing-function`
* `animation-delay`
* `animation-direction`
  * `normal`
  * `reverse` 反向
  * `alternate` 交替
  * `alternate` 反向交替
* `animation-fill-mode`
  * `none`
  * `forwards` 结束后保持结束状态
  * `backwards` 结束后保持开始状态
  * `both`
* `animation-iteration-count` 播放次数
  * `infinite` 无限
  * 数字，可为小数
* `animation-play-state` 播放状态
  * `paused` 暂停
  * `running` 启动

## 定义动画

* `@keyframes` 定义动画
  * 自定义动画名
  * 节点进度，百分比，`from, to`
  * 节点样式

```css
@keyframes slidein {
  from {
    transform: translateX(0%);
  }

  to {
    transform: translateX(100%);
  }
}
```
