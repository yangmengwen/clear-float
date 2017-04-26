# clear-float
### 浮动元素会引起的问题和解决办法
> 问题
```base
1. 父元素的高度无法被撑开，影响与父元素同级的元素
2. 与浮动元素同级的非浮动元素会跟随其后
3. 若非第一浮动元素，那么他前面的元素也要浮动，否则会影响页面显示结构
```
> 解决方法
```base
1. 额外标签，在浮动元素后面添加一个空的div标签设置clear:both属性
2. 使用伪类，给父元素添加clearfix样式

#parent:after {
  content:'';
  height: 0;
  visibility: hidden;
  display: block;
  clear: both;
  zoom: 1;
}
3. 浮动外部元素
4. 父元素设置overflow:hidden/auto，必须定义width或者zoom:1,不能定义height
```
### 常见浏览器兼容性问题与解决方法
```base
1. 不同浏览器的margin、padding值不同
解决方法：利用CSSReset重置样式{margin:0;padding: 0}
2. 快标签设置float后，又有横行的margin时，在IE6显示比设置的大
解决方法：在float标签样式中加入display：inline将其转化为行内元素
3. 透明度的兼容CSS设置
IE：filter：alpha（opacity=0）
Firefox： alpha：0
解决方法： 在CSS中同时设置上述两个属性
4. 图片默认有间距,几个img放在一起的时候，有些浏览器会有默认的间距
解决方法：去掉间距，使用float
```
