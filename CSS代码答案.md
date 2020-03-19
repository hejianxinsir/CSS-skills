## 文字两端对齐

```
<div class="one">
    <span>姓名</span></br>
    <span>联系方式</span>
</div>



.one{
  border: 1px solid red;
  height: 100px;
}

span{
  width: 5em;
  border: 1px solid green;
  display: inline-block;
  text-align: justify;
  overflow: hidden;
  height: 22px;
}

span::after{
  content: '';
  display: inline-block;
  border: 1px solid blue;
  width: 100%;
}
```

## 文本过长，过长的文字变成省略号
```
<div>
	asdfasdfasdfasdfsdfasdfasdfasdfsdfasdfa
	sdfasdfsdfasdfasdfasdfsdfasdfasdfasdfsdfas
	dfasdfasdfsdfasdfasdfasdfsdfasdfasdfasdfsd
</div>

div{
	border: 1px solid red;
	white-space: nowrap;
	overflow: hidden;
	text-overflow: ellipsis;
}
```

## 高 40px 的 div 里的文字垂直居中
```
<div class="one">
    asdfjasldfjlasdflasf
</div>

.one{
  outline: 1px solid red;
  padding: 7.3px 0;
  text-align: center;
}
```

## 多行文本，超出的部分变成省略号
```
<div>444444alsjlasdjgladsglasdfjlasdjflsaasldfkalsd fjlasdkjflasdkfjlasdf adf
  asdfsdfasdfasdfsdfas adsfasd fdsf asd  asdf sd asd asd asd asdf ad adsf
</div>


div{
  border: 1px solid red;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical; 
  overflow: hidden;
}
```








