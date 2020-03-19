CSS 进阶笔记

- div 或其他标签的高度并不等于内容的高度，标签的高度其实是字体设计师的建议高度。不同的字体的高度不同。

- link 引用 css 在里面写 media。即，只在你打印的时候加这些样式。
```
<link rel="stylesheet" href="xxx.css" media="print">
```

- 文字不换行：div 内文字很多，如何让它不自动换行?
```
<style>
div{
border: 1px solid red;
				white-space: nowrap;
				over-flow: hidden;
				text-overflow: ellipsis;   <!-- 超出的文本变成省略号（溢出省略） -->
}

<!-- 如果要两行文本变成省略号怎么办？ google text multi line text ellipsis -->
<!-- 显示两行文本，其他变成省略号 -->
div{
border: 1px solid red;
display: -webkit-box;
				 -webkit-line-clamp;
overflow: hidden;
}

</style>
<div>
1
2
3
3
4
5
6
6
6
7
7
7
.
.
.
</div>
```

- 怎么让一行 div 里的文字居中？
```
<div>eijldfjaoijwefjqwel;fjklwef</div>

<style>
div{
outline: 1px solid red;
				 line-height: 24px;
padding: 8px;


}
</style>
```
注意，不要写死高度。如果要让 div 的高度变成 40 px。line-height: 24px; padding: 8px 0; 就行了。你凑出 40px 就行了。有经验的人都不会写死高度，用 padding、line-height 凑就行了。这样的好处是，当你的文字很多的时候，不会出现 bug.

另外，border 是占高度的，outline 不占高度。

水平居中就是 text-align: center;

- margin 父子合并
运行以下代码查看
```
<div class="one">s</div>
<div class="dad">1
<div class="son">111</div>
</div>

.one{
border: 1px solid black;
}

.dad{
outline: 5px solid red;
}

.son{
border: 3px solid green;
margin: 10px;
}

/* 如果爸爸没有 border、且爸爸里没有内容挡住儿子，那么当给
	 儿子一个 margin 的时候，儿子与父亲的 margin 会合并，
	 这里的合并是指上下合并。 */
```

那如何解决 margin 父子合并？基于以上原因可以推导出，方法一：给爸爸一个 border-top 和 border-bottom 或者，方法二：给爸爸 padding-top  padding-bottom  1px 就行；或者方法三： 给爸爸加 overflow: hidden; 但方法三不要用！

关键是，儿子的 margin 能不能使 爸爸 变高，取决于爸爸是否有东西挡着儿子。

- 重点：div 的高度是由内部文档流中元素的总和决定的。文档流：内联元素从左到右，块级元素从上到下。块级元素每一个都另起一行。

- 脱离文档流：float: left/right、position: absolute、position: fixed; 都会脱离文档流，意思就是算高度的时候别算我。

- 重点：如果给一个子元素加 position: relative; top: 10px;（这样定位是相对于自己原来的位置定位） 计算父级高度的时候依然包含这个子元素；同时，加 top right 等等不会挤压其他元素，其他元素把它当做它还在原来的位置上一样。

- div 里的 div 如何垂直居中？
one : 如果子元素的宽度确定，左右居中就可以用 margin: 0 auto;
two: 如果父元素的高度确定，子元素的宽高确定，那么可以用：
```
.dad{
height: 100vh;
				box-sizing: border-box
}

.son{
width: 100px;
height: 100px;
position: absolute;
top: 0; right: 0; bottom: 0; left: 0;
margin: auto
}
```

three : 子元素上下左右居中(子元素不定宽高的时候)，在 dad 元素上加：
```
// IE 不支持，不用兼容 IE
.dad{  
display: flex;
				 justify-content: center;
				 align-items: center;
}
```

- 内联元素的margin padding 影响宽度，但是不影响高度。内敛内联元素的高度不受你加 padding 影响（但宽度受padding影响），虽然你有 padding ，但计算高度时不算你。（同理，margin 的上下也不影响高度，但margin的宽度是影响宽度的。）

- 实现一个 1:1 的 div，去 jsbin 里看一看。
```
div{
padding: 100%;
border: 1px solid red;
}
```

