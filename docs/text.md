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

* `text-align` 水平对齐方式，`left, right, center, justify`
* `text-align-last` 最后一行水平对齐方式
* `line-height` 行高，除了尺寸，还可以使用无单位数字，最终的行高等于字体大小乘以该数字，`1.5~2`比较合适
* `text-indent` 首行缩进

### 方向

* `writing-mode` 书写方向
  * `horizontal-tb` 水平书写，从上往下排列
  * `vertical-rl` 垂直书写，从右往左排列
  * `vertical-lr` 垂直书写，从左往右排列

  与书写方向对应的四个方位词

  | 逻辑属性 | 对应属性 | 逻辑属性 | 对应属性 |
  | :-- | :-- | :-- | :-- |
  | inline-start | left | block-start | top |
  | inline-end | right | block-end | bottom |
  | inline-size | width | block-size | height |

* `direction` 水平布局方向
  * `ltr`
  * `rtl`
* `text-orientation` 垂直方式书写时，单词书写方式

### 空白符处理

`white-space` 取值

| 值 | 空格和tab合并 | 自动换行 | `\n` 有效 |
| :-- | :-- | :-- | :-- |
| normal | ✅ | ✅ | ❌ |
| nowrap | ✅ | ❌ | ❌ |
| pre | ❌ | ❌ | ✅ |
| pre-wrap | ❌ | ✅ | ✅ |
| pre-line | ✅ | ✅ | ✅ |

### 文字溢出

* `text-overflow` 单行文字溢出
  * `clip` 隐藏
  * `ellipsis` 显示 `...`
* `word-break` 文字截断
  
  | 属性 | 最后一个词超长 | 单词超过一行 |
  | :-- | :-- | :-- |
  | normal | 显示在下一行 | 溢出 |
  | break-all | 截断显示在两行 | 截断显示在两行 |
  | break-word | 显示在下一行 | 截断显示在两行 |
  | keep-all | 显示在下一行 | 溢出 |

  `keep-all` 在CJK语言中不允许换行，其他与 `normal` 相同

* `overflow-wrap(word-wrap)` 单词过长溢出
  * `normal`
  * `anywhere`
  * `break-word` 文字截断
* `hyphens` 单词截断显示 `-` 连接
  * `none`
  * `manual`
  * `auto`
* `line-break` 处理带有标点的 `CJK` 的断句
  * `auto`
  * `anywhere`
  * `normal`
  * `loose`

## 自定义字体

```css
@font-face {
  font-family: 'zantrokeregular';
  src: url('fonts/zantroke-webfont.woff2') format('woff2'),
        url('fonts/zantroke-webfont.woff') format('woff');
}
```
