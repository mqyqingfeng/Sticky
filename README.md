# sticky

## 介绍

原生 JavaScript 实现的固定在顶部效果，兼容到 IE7+。

效果演示：[https://mqyqingfeng.github.io/Sticky/](https://mqyqingfeng.github.io/Sticky/)

## 兼容性

IE7+ 

## 依赖

原生 JavaScript 实现，无依赖。

## 下载

```js
git clone git@github.com:mqyqingfeng/Sticky.git
```

## 使用

```html
<script src="path/sticky.js"></script>
```

或者

```js
import Sticky from 'path/sticky.js'
```

## 示例

HTML 文件：

```html
<div id="sticky"></div>
```

JavaScript 文件：

```js
var sticky = new Sticky("#sticky");
```

## API

### 初始化

```js
var sticky = new Sticky("selector", options);
```

注意：当要兼容 IE7 的时候，不能传入选择符字符串，直接传入元素：

```js
var stickyElem = document.getElementById("sticky");
var sticky = new Sticky(stickyElem)
```

### options

**1.offset**

```js
var sticky = new Sticky("#sticky", {
    // 表示距离顶部 20px 的时候就固定
    offset: 20
});
```

### 事件绑定

从未固定状态到固定状态的时候：

```js
sticky.on("onStick", function() {
    console.log('固定在顶部')
})
```

从固定状态到未固定状态的时候：

```js
sticky.on("onDetach", function() {
    console.log('取消固定在顶部')
})
```

如果希望事件只执行一次，可以使用 once 进行绑定

```js
sticky.once("onStick", function() {
    console.log('固定在顶部')
})
```

### 类名

当固定在顶部的时候，会添加一个名为 `sticky` 的类名
