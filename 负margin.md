## 负margin的原理和运用

### 原理
- 文档流中 负margin 是不破坏高度的

    1. margin-top margin-left 负值是向上左拖动 也就说上和左位移

    2. margin-bottom margin-right 负值是减少bottom和right的值 撑大盒子的面积

- 浮动布局 中负margin 通常用来位移 如双飞布局

### 位移运用
- 绝对定位居中
````
.container {
    width: 1200px;
    height: 500px;
    margin: 0 auto;
    position: relative;
}
.box {
    width: 100px;
    height: 100px;
    background-color: #000;
    position: absolute;
    top: 50%;
    left: 50%;
    margin-left: -50px;
    margin-top: -50px;
}
````
````
<div class="container">
    <div class="box"></div>
</div>
````
 通过负margin 来给绝对定位的元素 位移

- 双飞布局 中间自适应 两边固定
````
 * {
    box-sizing: border-box;
}
.container {
    float: left;
    width: 100%;
}
.main {
    margin: 0 210px;
    height: 500px;
    background-color: blue;
}
.left {
    float: left;
    width: 200px;
    height: 200px;
    background-color: red;
    margin-left: -100%;
}
.right {
    float: left;
    width: 200px;
    height: 200px;
    background-color: green;
    margin-left: -200px;
}
````
````
<div class="container">
    <div class="main"></div>
</div>
<div class="left"></div>
<div class="right"></div>
````
 main留下对应的隔离值 left right 位移到对应的位置

### 撑大盒子的运用
````
* {
    margin: 0;
    padding: 0;
}
.container {
    width: 500px;
    margin: 20px auto;
    border: 1px solid #000;
}
.list {
    list-style: none;
    overflow: hidden;
    margin-right: -10px;
}
.box {
    float: left;
    width: 92px;
    height: 92px;
    background-color: red;
    margin-right: 10px;
    margin-bottom: 20px;
}
````
````
<div class="container">
    <ul class="list">
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
        <li class="box"></li>
    </ul>
</div>
````
 通过负margin-right 撑大的盒子的面积 放置box的margin-right的值
