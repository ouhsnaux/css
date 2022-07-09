# 语法

## 术语

```css
h1 {
  color: red;
  font-size: 5em;
}
```

* 一整块代码称为**规则**。
* 大括号前的 `h1` 称为**选择器**，选择需要应用样式的 `html` 元素。
* 括号内包含两条**声明**，用来修改 `html` 元素的样式。
* 每条声明包含**属性（color）**和**值（red）**。

## 使用

`html` 元素提供了 `class` 和 `style` 属性方便应用样式。

* 行内样式，直接在 `html` 元素中添加 `style` 属性

  ```html
  <p style="color: red; font-size: 5em">行内样式</p>
  ```

* 内部样式表，在 `<head>` 中添加 `<style>`

  ```html
  <head>
    ...
    <style>
      p {
        color: red;
        font-size: 5em;
      }
    </style>
  </head>
  ```

* 外链文件，在 `<head>` 中添加文件引用，在文件中添加样式规则

  ```html
  <head>
    ...
    <link rel="stylesheet" href="style.css">
  </head>
  ```

行内样式写法简单，无法复用，外链文件方便复用。

## 注释

```css
/* 这是CSS注释 */
```

## 空白符

样式声明之间的空白符无含义，会自动忽略，方便写出好看的代码。
