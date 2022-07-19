# 动画与过渡

## transform

* `transform-origin` 形变的基点

### 平移

* `translate(x, y)`
* `translateX, translateY, translateZ`
* `translate3d(x, y, z)`

### 旋转

* `rotate`
* `rotateX, rotateY, rotateX`

### 倾斜

### 缩放

### 3D

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
