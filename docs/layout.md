# 布局

## 盒模型

* `inline, block, inline-block`
* `BFC`
* `margin` 合并

## float

流式布局，需指定宽度，一般用于老式浏览器布局和图片环绕。

* `left` 向左浮动
* `right` 向右浮动

父级计算高度不包括浮动元素，会导致高度塌陷问题。
两种解决方案：

* 创建 `BFC`
* 创建伪元素清除浮动

```css
.class::after {
  display: block;
  content: '';
  clear: both;
}
```

### 浮动元素形状

* shape-outside
* shape-image-threshold
* shape-margin

## 定位

### position 取值

* `static` 正常布局
* `fixed` 固定定位，位置相对于视口固定
* `relative` 相对定位，相对原有位置定位
* `absolute` 绝对定位，一般根据祖先元素中相对定位元素进行定位，详见下方
* `sticky` 粘性定位，等于 `relative + fixed`

### 定位属性

* `top`
* `bottom`
* `left`
* `right`
* `z-index` 多层重叠时，值大的覆盖值小的

### 定位基准

1. `static` `relative` 和 `sticky` 的定位基准是最近非内联元素的祖先元素的 `content box`
2. `absolute`  最近 `position` 不是 `static` 的祖先元素的 `padding`
3. `fixed` 视口
4. `absolute` 或 `fixed` 的基准也可能是其他最近祖先元素
   1. `transform` 或 `perspective` 值不是 `none`
   2. `will-change` 的值是 `transform` 或 `perspective`
   3. `filter`
   4. `contain` 的值是 `paint`

## flex

弹性布局，主流布局方式。

### 容器

* `display: flex` 开启 `flex` 布局
* `flex-direction` 主轴方向，垂直方向为交叉轴
  * `row` 水平方向为主轴方向
  * `column`
  * `row-reverse`
  * `column-reverse`
* `flex-wrap` 溢出换行
  * `wrap` 换行
  * `nowrap`
* `flex-flow` `flex-direction + flex-wrap` 的缩写
* `justify-content` 水平轴对齐方式
  * `flex-start` 开端对齐
  * `flex-end` 结尾对齐
  * `center` 居中对其
  * `space-between` 空白在子元素之间均匀分布，开端和结尾无空白
  * `space-around` 开端和结尾的空白是子元素之间空白的一半
  * `space-evenly` 开端和结尾的空白与子元素之间空白一致
* `align-items` 单行交叉轴对齐方式
  * `flex-start, flex-end`
  * `center`
  * `stretch` 拉伸
* `align-content` 多行交叉轴对其方式
  * `flex-start` `flex-end`
  * `center`
  * `space-between` `space-around` `space-evenly`
  * `stretch`

### 子元素

* `flex-grow` 放大比例
* `flex-shrink` 缩小比例
* `flex-basis` 基础宽度
* `flex` `flex-grow + flex-basis + flex-basis`
  * `auto` `1 1 auto`
  * `none` `0 0 auto`
* `order` 自定义排序
* `align-self` 本元素交叉轴对齐方式，取值同 `align-items`

### 与 `margin: auto` 配合

## grid

网格布局，功能更加强大，浏览器支持不够。

### 容器属性

* `display: grid` 开启网格布局
* `grid-template-columns` 指定网格列数及列宽
* `grid-auto-columns` 定义未指定列的宽度
* `grid-template-rows` 指定网格行数及每行高度
* `grid-auto-rows` 定义未指定行的高度
* `column-gap` 列之间空白宽度
* `row-gap` 行之间空白高度
* `gap/grid-gap` `column-gap + row-gap`
* `grid-template-areas` 指定网格布局及命名

#### 值

* 常规尺寸
* `fr` 弹性布局，根据数字均分剩余空间
* `minmax(min, max)` 最终结果处于区间内，值可以是上面的值和 `auto`
* `repeat(time, val)` 重复值多少次，值可以是上面3个值，次数可以是 `auto-fill`

  ```css
  /* 实现每列宽度相同，最小宽度200px  */
  .class {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  }
  ```

### 子元素属性

* `grid-column` 指定占据列，`grid-column-start + grid-column-end`
* `grid-row` 指定占据行 `grid-row-start, grid-row-end`
* `grid-area` 指定占据网格名，与 `grid-template-area` 对应

  ```css
  .container {
    display: grid;
    grid-template-areas:
        "header header"
        "sidebar content"
        "footer footer";
    grid-template-columns: 1fr 3fr;
    gap: 20px;
  }

  header {
    grid-area: header;
  }

  article {
    grid-area: content;
  }

  aside {
    grid-area: sidebar;
  }

  footer {
    grid-area: footer;
  }
  ```

## 媒体查询

根据媒体类型和属性使用对应的样式规则

```css
/* 屏幕宽度不超过800px时使用 */
@media screen and (min-width: 800px) {
  .container {
    margin: 1em 2em;
  }
}
```

* 媒体类型 `screen, print`
* 特性，宽高 `min-width: 30em`
* 逻辑操作符，and, not, only, `,`

### 打印机常用属性

* `@page` 选择器
  * `page-break-inside: avoid` 该元素不会被分页截断
  * `page-break-before: always` 该元素另起一页

## 多列布局

报纸的布局。每列宽度一致，不能单独更改某一列宽度。

### 属性

* `column-count` 列数
* `column-width` 列宽
* `column-gap` 列间隙
* `column-rule` 列之间的分割线，类似于 `border`

### 子元素属性

* `column-span: all` 可占据所有列
* `break-inside: avoid` 避免同一元素在多列分割展示

## 特性查询

针对支持某些特性的浏览器，包含该样式规则

```css
@supports (display: grid) {
  div {
    display: grid;
  }
}

@supports not (display: grid) {
  div {
    float: right;
  }
}
```

## 实现响应式布局

* 布局手段
  * `flex`
  * `grid`
  * 媒体查询
* 响应式单位
  * 百分比
  * `vw vh` 视口宽高
  * `rem` 根据 `html` 元素字体大小计算
  * `em` 根据父元素字体大小计算
* `html` 使用响应式图片

## flex 垂直占满高度

父元素竖向布局，第一个子元素固定高度，flex:none
第二个子元素高度100%，flex:auto
有可能出现滚动条，第二个子元素的高度与父元素高度一致
解决方案：

1. 第二个子元素添加overflow:auto
2. 第二个子元素height: 0
