css 示例片段代码

记录我们平时常用到的 CSS 片段，使用这些 CSS 可以帮助我们解决许多实际项目中遇到的问题，记录下来方便日后查找和使用。

1. <font color=#ff0000 size=3 face="黑体">清除浮动</font>

**场景**：浮动给我们的代码带来的麻烦，想必不需要多说，我们会用很多方式来避免这种麻烦，其中我觉得最方便也是兼容性最好的一种是，在同级目录下再创建一个：

```
<div style="clear:both;"></div>；
```

不过这样会增加很多无用的代码。此时我们用:after这个伪元素来解决浮动的问题，如果当前层级有浮动元素，那么在其父级添加上 clearfix 类即可。

```
// 清除浮动
.clearfix:after {
  content: "\00A0";
  display: block;
  visibility: hidden;
  width: 0;
  height: 0;
  clear: both;
  font-size: 0;
  line-height: 0;
  overflow: hidden;
}
.clearfix {
  zoom: 1;
}
```
