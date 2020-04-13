flex 布局

- flex-direction  方向
- flex-wrap: wrap/nowrap  换行、不换行
- flex-flow: direction wrap;  是上面两个的简写，分别是方向和是否换行；
- 主轴是由方向决定的。justify-content 就是主轴方向的对齐方式。
- 默认情况下，水平线是主轴；如果给 flex: column 那么垂直线就是主轴。
- align-items 侧轴对齐方式。
- align-content  多行/列内容对齐方式

## flex item 的属性(用在子元素上)

- flex-grow  某个子元素吃掉多余的空间。flex-grow: 2; flex-grow: 1; flex-grow: 3，这样就按照 2:1:3 的比例分配给三个子元素了。 
- flex-shrink 按比例收缩，与flex-grow 相反。
- flex-basis  flex-basis: 200px;
- flex: x y z  就是上面三个的缩写，分别写 grow shrink basis
- order 比如如果只有三个子元素。order: 1  放在前面  order: 2 接着order:1 放，order: 3 放最后。
- align-self: center  让每一个孩子自己选择自己的对齐方式。

## 手机页面布局
CSS
```
*{
padding: 0;
margin: 0;
}
.wrapper{
border: 1px solid red;
display: flex;
flex-direction: column;
height: 100vh;
}

header, footer{
background: #ccc;
}

main{
flex-grow: 1;
overflow: auto;
}

ul{
list-style: none;
height: 100px;
background: red;

display: flex;
}

ul>li{
border: 1px solid black;
margin: 0 1px;
width: 25%
}
```

HTML
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<title>JS Bin</title>
</head>
<body>
<div class="wrapper">
<header>header</header>
<main>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
<p>main</p>
</main>
<footer>
<ul>
<li></li>
<li></li>
<li></li>
<li></li>
</ul>
</footer>
</div>
</body>
</html>
```

## 产品列表布局
HTML
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<title>JS Bin</title>
</head>
<body>
<ul>
<li></li>
<li></li>  
<li></li>  
<li></li>  
<li></li>  
<li></li>  
<li></li>  
<li></li>  
<li></li>  
</ul>


</body>
</html>
```

CSS
```
*{
margin: 0;
padding: 0;
list-style: none;
}

ul{
border: 1px solid gray;
display: flex;
width: 350px;
justify-content: space-between;
flex-wrap: wrap;
}

ul li{
border: 1px solid red;
width: 100px;
height: 100px;
}
```

## PC 页面布局
HTML
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<title>JS Bin</title>
</head>
<body>

<header></header>
<div class="content">
<main></main>
<aside></aside>
<nav></nav>
</div>
<footer>

</footer>

</body>
</html>
```

CSS
```

*{
margin: 0;
padding: 0;
}
header{
height: 100px;
background: gray;
}
.content{
display: flex;
}
.content>aside{
width: 20%;
background: lightgray;
order: 1;
}
.content>main{
height: 500px;
background: red;
flex-grow: 1;
order:2;
}
.content>nav{
width: 100px;
order: 3;
}
footer{
height:100px;
background: gray;
}
```
