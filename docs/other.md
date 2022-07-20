# 其它

## 交互

* `cursor` 鼠标样式
* `user-select` 控制文本能否被选中
* `resize` 是否可调整尺寸，不能作用于行内元素和 `overflow:visible` 的元素
  * `horizontal`
  * `vertical`
  * `both`
  * `none`
* `scroll-behavior: smooth` 平滑滚动

## 引用文件

* @import 引用其它文件

## 生成内容

* `content`
  * 字符串
  * 图片 `url(), linear-gradient`
  * `open-quote, close-quote`，配合 `quotes` 使用
  * `counters(val, list-style-type)`
  * `attr()` 元素属性，应用于伪元素时，对应父元素的属性
  * 可以写多个
* `quotes`
  * `quotes: "'" "'";` `''`
  * `quotes: "《" "》" "<" ">";` 嵌套引号，外部使用 `《》`，内部使用 `<>`
* 伪元素, `::before, ::after, ::marker` 一般在这些伪元素上使用 `content`

## 自定义变量

* `--` 定义变量 `--dir: left`
* `var(name, fallback)` 使用变量 `var(--dir)`，第二个参数为候补内容

变量具有作用域，只可以在本元素及子元素中使用，在 `:root` 中定义全局变量

使用 `js` 操作变量

```js
// 设置
element.style.setProperty("--my-var", jsVar + 4);

// 查询
element.style.getProperty("--my-var");
```

## filter

添加滤镜，调整内容的颜色。

* `url()` 使用svg
* `blur` 虚化，使用距离，单位为 `px`
* `grayscale` 颜色消除器，使用百分比
* `brightness` 调整亮度，百分比
* `contrast` 对比度，百分比
* `invert` 反转 百分比
* `hue-rotate` 色调旋转，单位deg
* `drop-shadow` 阴影，包括盒子里的内容

可以同时使用多个值。

## 工具

兼容性检测：[Can I use](https://caniuse.com/)

## 预处理器

当原生 `css` 变得越来越大，越来越复杂，变得难以维护。

预处理器完全兼容原生 `css`，添加了许多新特性，代码更强壮易读可维护，编译后可生成 `css`。

[Sass](https://github.com/ouhsnaux/sass)
