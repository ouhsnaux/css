# 规范

## 文件结构

* `reset.css` 重置并统一浏览器默认样式，包括滚动条
* `common.css` 常用样式，与具体业务无关，即使换了一个系统，依然能用。
  比如清除浮动，文字溢出换行等。
* `global.css` 全局样式。比如按钮样式，组件布局。
* 其它，比如定义变量，ui组件库样式重置

## 代码风格

* 选择器
  * 属性和值全小写
  * 少使用*和id选择器
  * 嵌套不超过5级
* 属性
  * 尽量使用简写，方便后续改单个样式
  * 声明顺序：布局，盒模型，背景，文字，动画
* 值
  * 0不要加单位
  * 尽量不使用 `!important`
* 左右结构给左元素添加右边距，给上元素添加下边距

## 避免 `class` 重名

* 全局样式命名应与实际效果相关。比如 `text-ellipsis` 文字溢出使用 `...`，`clear-float` 清除浮动。
* 组件样式使用 `scoped`，`module` 等模块化功能。
* 命名使用 `B__E--M` 思想
  * `Block` 具有独立意义
  * `Element` 块的内部元素
  * `Modifier` 修饰符，比如 `active, primary, disabled`
* `ATOM, TailWindCSS` class只跟样式有关，每个类对应一种属性声明
