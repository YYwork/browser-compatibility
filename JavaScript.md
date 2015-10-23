# JavaScript 总结

* jquery 支持 ie8 的版本为 1.x, 2.x 以上不支持 ie8

* 不要使用 window.open()

该方法已被广告弹窗乱用，很多浏览器在非用户触发时禁止使用。

* eval

* event.x与event.y问题

    (1)现有问题：在IE中，event对象有x,y 属性，Firefox中没有。
    (2)解决方法：在Firefox中，与event.x 等效的是 event.pageX。可以使用：

```js
  mx = event.x ? event.x : event.pageX;
```

* window.event

  (1)现有问题：使用window.event无法在Firefox上运行
  (2)解决方法：

```html
  <input type="button" name="someButton" value="提交" onclick="javascript:gotoSubmit(event)"/>
  ...
  <script language="javascript">
      function gotoSubmit(evt) {
          evt = evt ? evt : (window.event ? window.event : null);
          ...
          alert(evt);             // use evt
          ...
      }
  </script>
```

* attachEvent和addEventListener

    (1)现有问题：IE中使用attachEvent来添加事件，Firefox中使用addEventListener。
    (2)解决方法：如下，注意事件参数的区别，一个是click，一个是onclick。

```js
  if (document.attachEvent) document.attachEvent("click", clickHandler,false);
  else document.addEventListener("onclick",clickHandler);
```

* const

    (1)现有问题：在IE中不能使用const关键字。如const constVar = 32;在IE中这是语法错误。
    (2)解决方法：不使用const，以var代替。

* 多余的逗号

  (1)现有问题：firefox中对象文字常量容许多余的逗号，在IE中不允许。下面语句在IE中非法。
      `var obj = { 'key' : 'aaa', }`
  (2)解决方法：去掉多余逗号。

