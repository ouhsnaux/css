# 文字

## 样式

* `color` 文字颜色
* `font-family` 字体
* `font-size` 大小
* `font-style` 样式
  * `normal`
  * `italic` 斜体
  * `oblique` 文字倾斜
* `font-weight` 字重
  * `100~900`的数字，`500`为正常
  * `bold` 粗体
  * `normal` 正常
* `text-transform`
  * `none`
  * `uppercase` 转为大写
  * `lowercase` 转为小写
  * `capitalize` 首字母大写
* `text-decoration`
  * `text-decoration-line` 可添加多个值
    * `none` 无
    * `underline` 下划线
    * `overline` 上划线
    * `line-through` 删除线
  * `text-decoration-style` 样式，`dashed, dotted, double, solid, wavy`
  * `text-decoration-thickness` 线宽
  * `text-decoration-color` 线色
* `text-shadow` 文字阴影，包含偏移量，模糊度和颜色，使用逗号分隔可添加多个阴影。

## 布局

### 方向

`writing-mode` 书写方向

* `horizontal-tb` 水平书写，从上往下排列
* `vertical-rl` 垂直书写，从右往左排列
* `vertical-lr` 垂直书写，从左往右排列

与书写方向对应的四个方位词

* `inline` 对应文字书写方向
  * `inline-start` 对应默认布局的 `left`
  * `inline-end` 对应默认布局的 `right`
  * `inline-size` 对应默认布局的宽度
* `block` 对应文字排列方向
  * `block-start` 对应默认布局的 `top`
  * `block-end` 对应默认布局的 `bottom`
  * `block-size` 对应默认布局的 `height`

### 文字布局

* `text-align` 水平对齐方式，`left, right, center, justify`
* `line-height` 行高，除了尺寸，还可以使用无单位数字，最终的行高等于字体大小乘以该数字，`1.5~2`比较合适
* `text-indent` 首行缩进
* `text-overflow` 文字溢出
  * `clip` 隐藏
  * `ellipsis` 显示 `...`
* `white-space` 空白符和换行符
  * `normal` 空白符合并，自动换行
  * `nowrap` 空白符合并，禁止换行
  * `pre` 保留原有格式，不自动换行
  * `pre-wrap` 保留原有格式，并自动换行
  * `pre-line` 空白符合并，自动换行
  * `break-spaces`
* `word-break`
* `direction`
* `hyphens`
* `line-break`
* `text-align-last`
* `text-orientation`
* `overflow-wrap`

`white-space` 取值

| 值 | 空格和tab合并 | 自动换行 | `\n` 有效 |
| :-- | :-- | :-- | :-- |
| normal | ✅ | ✅ | ❌ |
| nowrap | ✅ | ❌ | ❌ |
| pre | ❌ | ❌ | ✅ |
| pre-wrap | ❌ | ✅ | ✅ |
| pre-line | ✅ | ✅ | ✅ |
