# 浏览器兼容

[百度统计 浏览器市场份额](http://tongji.baidu.com/data/browser/)

1. win7 默认IE版本 IE8。
2. windows系统会总提示让你升级，而且就算是使用老的系统，比如xp系统，很多ghost版本的系统都会更新ie浏览器。
3. 大部分网吧默认是ie8浏览器。
4. 一些事业单位默认是ie8浏览器。
5. 360  360安全浏览器
6. IE6， IE7 估计只是那些不经常使用浏览器的用户还在使用，它们没必要升级，也不知道还有其他浏览器。

IE8 是唯一一个不是现代浏览器，而在中国市场上依旧占据很大市场的傻X浏览器。

通过以下方式 兼容 IE8.

## CSS Reset

>
  由于早期的浏览器支持和理解的 CSS 规范不同，导致浏览器在渲染页面时效果不一致，出现很多兼容性问题。

  ```
    <link href="//cdn.bootcss.com/normalize/3.0.3/normalize.css" rel="stylesheet">
  ```

 * [Normalize](https://github.com/necolas/normalize.css/)


## HTML5 CSS3 兼容 IE

  ```
    <!--[if lt IE 9]>
      <script src="//cdn.bootcss.com/html5shiv/3.7.2/html5shiv.min.js"></script>
      <script src="//cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
      <script src="//cdn.bootcss.com/selectivizr/1.0.2/selectivizr-min.js"></script>
    <![endif]-->
  ```

  * [html5shiv -- 让 IE6-8 识别 HTML5 新的元素](https://github.com/aFarkas/html5shiv/tree/master/dist)
  * [Respond -- 让 IE6-8 支持 CSS3 Media Query](https://github.com/scottjehl/Respond/tree/master/dest)
  * [Selectivizr -- 让 IE6-8 支持 CSS3 伪类和属性选择器](https://github.com/keithclark/selectivizr)

## meta标签


#### 强制IE8使用最新的内核渲染页面

```
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
```

#### 360双核浏览器 适用房 Webkit 渲染
```
<meta name="renderer" content="webkit">
```


## 使用 [css3pie](http://css3pie.com/) 支持 css3 特性

```
border-radius
box-shadow
border-image
multiple background images
linear-gradient
```
等

## css 属性

#### max-width

#### 嵌套 inline-block 下 padding 元素重叠

解决方法是使用float: left替代display: inline-block实现水平布局。

#### last-child

设置一个.last的class

#### placeholder

IE8下不支持HTML5属性placeholder，不过为解决此问题的js插件挺多的，比如：[jquery-placeholder](https://github.com/mathiasbynens/jquery-placeholder)。

#### AlphaImageLoader, Blur滤镜

background-size: cover

```
filter: progid:DXImageTransform.Microsoft.AlphaImageLoader(enabled=Enabled, sizingMethod=Size , src=URL)
```

如果你在此背景之上放置了链接，那这个链接是无法点击的。一般情况下的解决办法是为链接或按钮添加position:relative使其相对浮动。

filter blur

```
filter: progid:DXImageTransform.Microsoft.Blur(PixelRadius='10');

-webkit-filter: blur(10px);
-moz-filter: blur(10px);
```


[am-team](http://am-team.github.io/amg/dev-exp-doc.html)
[移动端模拟弹窗](http://www.zuojj.com/archives/1554.html)
[IE8+兼容经验小结](http://www.hustlzp.com/post/2014/01/ie8-compatibility)

