## css 属性兼容

#### max-width

#### 嵌套 inline-block 下 padding 元素重叠

解决方法是使用float: left替代display: inline-block实现水平布局。

#### last-child

设置一个.last的class

#### placeholder

IE8下不支持HTML5属性placeholder，不过为解决此问题的js插件挺多的，比如：[jquery-placeholder](https://github.com/mathiasbynens/jquery-placeholder)。

#### AlphaImageLoader, Blur滤镜

background-size: cover

```css
filter: progid:DXImageTransform.Microsoft.AlphaImageLoader(enabled=Enabled, sizingMethod=Size , src=URL)
```

如果你在此背景之上放置了链接，那这个链接是无法点击的。一般情况下的解决办法是为链接或按钮添加position:relative使其相对浮动。

filter blur

```css
filter: progid:DXImageTransform.Microsoft.Blur(PixelRadius='10');

-webkit-filter: blur(10px);
-moz-filter: blur(10px);
```