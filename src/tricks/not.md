# not

当我们渲染列表时，为了分割，给每一项设置 `border-bottom: 1px solid #ddd`，
然后再删除最后一个元素的边框。

其实可以一步到位

```css
:not(:last-child) {
  border-bottom: 1px solid #ddd;
}
```
