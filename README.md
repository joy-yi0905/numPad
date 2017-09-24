# numpad

一款基于zepto的数字键盘，主要应用于移动端。

模拟input的一些特性。比如：

- 光标待输入状态
- 当输数大于最大宽度时，总是显示最新输入的内容

当输入框在页面底部时，不会被numpad遮挡。

### 如何使用

- 首先引入插件的样式

```html
<link rel="stylesheet" href="src/zepto.numpad.css">
```

- 然后再引入zepto.numpad.js和 zepto.js

```html
<script src="src/zepto.min.js"></script>
<script src="src/zepto.numpad.js"></script>
```

- 最后在页面里，为需要的 `<input>` 元素添加方法。 相关示例代码：

```html
<input type="text" placeholder="输入数字" class="input-number" />

<script>
$('.input-number').numpad();
</script>
```

除此之外，numpad 还提供了一些自定义属性，有 `digit`、`border` 和 `callback`，分别表示 小数点位数、是否需要边框、输入回调。你可以像这样使用它们：

```js
$('.input').numpad({
  digit: 3,
  callback: function(value, isNumber) {
    if (isNumber) {
	  console.log(value);
	} else {
	  console.log('input value is not number');
	}
  }
});
```

上面代码，设置了 `.input` 元素只能输入小数点后三位，并进行了回调处理。

具体使用，详见下表。


### 参数

numpad 方法接收一个对象作为参数，该参数包含了 `digit`、`border`、`callback` 三个选项。默认情况下，它们的取值如下：

| **参数** | **描述** | **默认值** | **格式** |
|----------|----------|------------|----------|
| digit | 小数点后的位数 | 2 | number |
| border | 模拟input是否需要边框 | false |true、或者 "1px solid red"  |
| callback | 每次输入回调 | 空函数 | 包含参数 value、isNumber |


numpad演示：[demo](http://joy-yi0905.github.io/numpad/demo/index.html)