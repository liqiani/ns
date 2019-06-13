---
typora-root-url: 笔记图片
---

## 第一天

### html

#### 1.常用标签

```html
    *<sub>下标
	*<sup>上标
	*<del>删除线
	*<b>加粗
	*<i>斜体
	*<!-- align是img标签的属性，通过该属性可以定义文字与图片的对齐方式。值： top 上 ，center中， bottom 下-->
		<img src="../img/02.jpg" title="图片8" width="100px" height="130px" align="bottom"/>校园
	*<!-- 1. 定义锚点  <a name='锚点名'>...</a>
		 2. 使用锚点 <a href="#tiyu">体育</a>
		    通过#引用锚点名-->	
      cellspacing="0" 单元格与单元格之间的距离
      cellpadding="20" 内容距离边框的距离
```

#### 2.大体格式

```html
<html>
	<head>
		<meta charset="utf=8">
		<title>标题</title>
		<!-- 链接外部文件 -->
		*<link rel="stylesheet" href="css/style.css" />
		*<script type="text/javascript" src="js/test.js"></script>
		...
	</head>
	<body>
		主体内容
		  ---1. 标题标签  <h1>~<h6>  加粗  逐渐变小  块级元素
		  ---2. <font color='red'></font>
					属性： 标签属性   key = value 
					一个标签可以有多个属性
		  ---3. 字体： <b> <i> <del> <sub> <sup>
		  ---4. 图片:  <img src='（绝对）|（相对）路径' title=''/>  单标签  行内元素
		        绝对：  c:/files/images/01.jpg
				相对:   ..  返回上一级   ../images/01.jpg
		  ---5. 超级链接: a 
		        三种：
				   1. 外网：  <a href='http://www.baidu.com' target='__blank'>链接文字</a>
				   <a href=""><img src='..'></a>
				   2. 本项目内链接： <a href='index.html'></a>
				   3. 锚点: 位置定位
					<a name='锚点名'></a>
					<a href='#锚点名'>...</a>
	</body>
</html>
```

## 第二天

### html

#### 1.表格

```html
<!--	
      标签： table   tr行   td单元格
      table:
            属性： border 边框 
            cellspacing="0" 单元格与单元格之间的距离
            cellpadding="20" 内容距离边框的距离
            align： 对齐方式  指的是表格整体
            width: 可以是具体的像素也可以是百分比
      tr: 
			align  该行的内容对齐方式。
			bgcolor 背景颜色
      td: 
			align  仅仅对此单元格的内容进行对齐方式设置
			行合并  rowspan=""
          	列合并  colspan=""
      th: head  作为头部标签  文字特点：加粗 居中
-->
```

#### 2.列表

```html
1.无序列表 ul...li     
	li块级元素
	ul的属性：--->style="list-style:none;"--->不显示样式**
			 --->type="circle"--->空心圆
			 --->type="disc"  --->实心圆
			 --->type="square"--->实心正方体
2.有序列表 ol...li
3.自定义列表 dl...(dt...dd)
	<h1>自定义列表</h1>
	<div style="width: 300px;">
		<dl>
			<dt><img src="img/010.jpg"></dt>
			<dd style="margin-left: 10px;font-size: 10px;">男士牛仔裤 					<span style="color: red;">价格:299</span>
			</dd>
		</dl>
	</div>		
```

#### 3.表单

```html
<!-- 
	form表单：  
		action 
			提交的地址
			<input type="submit" value="提交"/> --->与action绑定
		method 
			请求方法：get
            http://127.0.0.1:8848/Day12Web/demo04_%E8%A1%A8%E5%8D%95.html?				username=admin123&password=123456&gender=boy
            请求方法: post
               	http://127.0.0.1:8848/Day12Web/index.html
                提交的数据在form data(请求request的头部)
                隐藏在请求头中，username:admin123(key-value)
            get请求（默认的请求），所有提交的请求参数都会拼接在URL的后面。
					安全性低。URL的长度是有限的，数据容易丢失。
            post请求：将所有的数据保存在请求中，没有长度的限制。
		
		enctype='application/x-www-form-urlencoded'  默认
			文件上传必须使用的：enctype="multipart/form-data"
-->
<form action="index.html" method="get">
		用户名:
		    <input type="text" placeholder="用户名/手机号码" name="uname"/>
		密&nbsp;&nbsp;&nbsp;码:
		    <input type="password" placeholder="密码" name="password"/>
		性&nbsp;&nbsp;&nbsp;别:
			<input type="radio" name="gender" value="boy" checked />男 
			<input type="radio" name="gender"value='girl' />女
		爱&nbsp;&nbsp;&nbsp;好:
			<input type="checkbox" name="hobbys" value='online' />上网
			<input type="checkbox" name="hobbys" value='basketball' />篮球
			<input type="checkbox" name="hobbys" value='football' />足球
		城&nbsp;&nbsp;&nbsp;市:
			<select name="province">
				<option value="beijing">北京市</option>
				<option selected>河北省</option>
				<option value="liaoning">辽宁省</option>
			</select>
		评价:
			<textarea name="comment" cols="50" rows="5"></textarea>
		文件上传:
			<input type="file" name="upload" />
		隐藏框：
			<input type="hidden" value="1" name="id" />
		年月日：	
			<input type="date" name="date"/>
		url地址：
			<!-- http://www.baidu.com -->
			<input type="url" name="url"/>
		该框只允许输入数字：
			<input type="number" name="number"/>
		满足电子邮箱格式：
			<input type="email" name="email"/>
		提交按钮：
			<input type="submit" value="提交"/> --->与action绑定
			<input type="button" value="提交" onclick=""/> --->结合onclick使用
		重置按钮：	
			<input type="reset" value="重置" />
	</form>
```

#### 4.div span

## 第三天

### css

#### 1.常见样式

```css
border-bottom: 1px red dashed;
border-width: 0px ;//边线宽度
border-radius: 5px;//边线圆角
cursor: pointer;/*小爪子*/
text-decoration: none;//下划线不显示
line-height和height组合到一块儿，就会在垂直方向居中//块级记得转化为行内块元素
display: inline-block;/*显示为行内块元素*/
line-height:20px;行高
background-position: -120px -80px;//背景图片定位
list-style: none;/*ul的不显示样式的属性*/
display: none;/* 隐藏 */
display: block;/* 显示 */
margin:外边距//块与块之间的距离
padding：内边距//内容距离边框的距离
```

![mar-pad](/mar-pad.PNG)

#### *三个块并排

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>使用全局</title>
		<link rel="stylesheet" href="css/global.css" />
		<style>
			#order{
				width: 100%;
				height: 500px;
			}
			#movie_left,#movie_center,#movie_right{
				width: 32%;
				height: 500px;
				float: left;
				margin-left: 1%;
			}
			#movie_left{
				background-color: #FF0000;
			}
			
			#movie_center{
				background-color: #0000FF;
			}
			
			#movie_right{
				background-color: darkkhaki;
			}
		</style>
	</head>
	<body>
		<div id="order">
			<div id="movie_left"></div>
			<div id="movie_center"></div>
			<div id="movie_right"></div>
		</div>
	</body>
</html>
```

#### *隐藏显示

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>隐藏</title>
		<style>
			#container {
				width: 400px;
				background-color: lightgray;
				border: 1px red solid;
				padding-left: 15px;
				margin: 10px;
				float: left;
			}
			ul {
				list-style: none;
				padding-left: 0px;
			}
			li{
				margin-bottom: 5px;
			}
			h3 {
				color: red;
				float: left;
				margin-left: 30px;
			}	
			#container>h3>ul{
				display: none;
				position: absolute;
				top: 70px;
				left: 30px;
				font-size: 70%;
			}
			#container>h3:hover ul{
				display: block;
			}
		</style>
	</head>
	<body>
		<div id="container">
			<h3>今日热点
				<ul>
					<li>个税专项附加扣除遇到问题怎么解？</li>
				</ul>
			</h3>
			<h3>今日热点
				<ul>
					<li>日本吸毒女星酒井法子，来中国在线乞讨？网友怒了</li>
				</ul>
			</h3>
		</div>
	</body>
</html>
```

#### *导航栏

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>导航栏</title>
		<link rel="stylesheet" href="css/global.css" />
		<style>
			#order{
				width: 100%;
				height: 50px;
				background-color: #3E3D43;
				line-height: 50px;
				color: #FFFFFF;
			}
			ul{
				padding-left: 0;
			}
			li{
				width: 32%;
				list-style: none;
				float: left;
				margin-left: 1%;
				text-align: center;
			}
			li:hover{
				border-top: 2px red solid;
				height: 48px;
				background-color: black;
			}
		</style>
	</head>
	<body>
		<div id="order">
			<ul style="margin: 0 auto;width: 50%;">
				<li>haha1</li>
				<li>haha2</li>
				<li>haha3</li>
			</ul>
		</div>
	</body>
</html>

```



## 第四天

### css

#### 1.缺小角

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>缺小角</title>
		<style type="text/css">
			#del{
				border-top: 5px transparent solid;
				border-left: 5px transparent solid;
				border-bottom: 5px white solid;
				border-right: 5px white solid;
				display: inline-block;
				position: absolute;
				top: 38px;
				left: 38px;
			}
			#tol{
				border: 20px #8B0000 solid;
				display: inline-block;
			}
		</style>
	</head>
	<body>
		<span id="del"></span>
		<div id="tol"></div>
	</body>
</html>

```

#### 2.定位

##### 相对定位

```html
*相对自己原来的位置进行定位,要结合left，top进行位置的移动。
*在使用相对定位时，就算元素被偏移了，但是他仍然占据着它没偏移前的空间
*我们可以设置它的z-index属性来调整它的堆叠顺序。//z-index=1..越大就在上边
```

![relative](/relative.PNG)

##### 绝对定位

```html
绝对定位其实也是类似浮动的。
<!--那么绝对定位是如何定位的呢？首先，如果它的父元素设置了除static之外的定位，比如position:relative,或者position:absolute以及position:fixed，那么它就会相对于它的父元素来定位，位置通过left , top ,right ,bottom属性来规定，如果它的父元素没有设置定位，那么就得看它父元素的父元素是否有设置定位 ，如果还是没有就继续向更高层的祖先元素类推，总之它的定位就是相对于设置了除static定位之外的定位（比如position:relative）的第一个祖先元素，如果所有的祖先元素都没有以上三种定位中的其中一种定位，那么它就会相对于文档body来定位（并非窗口,相对于窗口定位的是fixed）
绝对定位的元素相对于谁来定位，我们就把这个"谁"叫着参照物，我们结合上面的讲解来看看下图就明白了 ：-->
```

![absolute1](/absolute1.PNG)

![absolute2](/absolute2.PNG)



##### 固定定位

> 京东右侧栏

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>京东右侧栏</title>
		<link rel="stylesheet" href="css/global.css" />
		<style>
			body{
				height: 1000px;
			}
			#outter{
				width: 20px;
				height: 300px;
				background-color: #AAAAAA;
				position: fixed;
				top: 50px;
			}
			ul{
				list-style: none;
				padding-left: 0;
			}
			li{
				width: 30px;
				height: 35px;
				background-image:url(../img/sprite.service.png);
				margin: 10px 0;
				position: relative;
				margin-left: 20px;
			}
			span{
				width: 60px;
				height: 35px;
				line-height: 35px;
				background-color: red;
				color: white;
				display: inline-block;
				font-size: 92%;
				position: absolute;
				left: 30px;
				display: none;
			}
			li:hover span{
				display: block;
			}
		</style>
	</head>
	<body>
		<div id="outter">
			<ul>
				<li style="background-position: 0px -30px;">
					<span>京东会员</span>
				</li>
				<li style="background-position: 0px -30px;">
					<span>京东客服</span>
				</li>
			</ul>
		</div>
	</body>
</html>
```

#### 3.小扩展css3

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style>
			div {
				width: 200px;
				height: 200px;
				border: 1px red solid;
				-webkit-perspective: 400;
				-webkit-transform-style: preserve-3d;
				-webkit-transition-property: transform;
				-webkit-transition-duration: 1s;
				margin: 50px;
			}
			#rotatex {
				display: inline-block;
				width: 200px;
				height: 200px;
				background-color: #64B7CB;
				-webkit-transform: rotateZ(45deg);
				-moz-transform: rotateZ(45deg);
			}			
			#translate{
				display: inline-block;
				width: 200px;
				height: 200px;
				background-color: #FFD700;
				-webkit-transition-duration: 2s;
			}			
			#translate:hover{
				-webkit-transform: translate(50px,0px);
				-webkit-transition-duration: 2s;
			}			
			#scale{
				display: inline-block;
				width: 200px;
				height: 200px;
				background-color: palegreen;
				-webkit-transition-duration: 5s;
			}			
			#scale:hover{
				-webkit-transform: scale(0.5,0.5);
				-webkit-transition-duration: 5s;
			}			
			#skew{
				display: inline-block;
				width: 200px;
				height: 200px;
				background-color:blue;
				-webkit-transition-duration: 2s;
			}			
			#skew:hover{
				-webkit-transform: skew(90deg,30deg);
				-webkit-transition-duration: 2s;
			}
		</style>
	</head>
	<body>
		<div>
			<!-- 行内元素 -->
			<span id="rotatex"></span>
		</div>
		<!-- 平移 -->
		<div>
			<!-- 行内元素 -->
			<span id="translate"></span>
		</div>
		
		<!-- 伸缩 -->
		<div>
			<!-- 行内元素 -->
			<span id="scale"></span>
		</div>
		
		<!-- 扭曲 -->
		<div>
			<!-- 行内元素 -->
			<span id="skew"></span>
		</div>
	</body>
</html>
```

## 第五天

### js

#### 小问题

```javascript
alert('我的名字是:'+name+',我今年:'+age+"岁");------弹出提示框
document.write(result);-------浏览界面输出
console.log();--------控制台输出
```

> href与src

```javascript
href 表示超文本引用（hypertext reference），在 link和a 等元素上使用。
<a href=''></a>
<link rel='stylesheet' href='xxx.css'/>

src 表示来源地址，在 img、script、iframe 等元素上。
<img src='' />
<script type="text/javascript" src="js/test.js"></script>

src 的内容，是页面必不可少的一部分，是引入。href 的内容，是与该页面有关联，是引用。区别就是，引入和引用

```

> ++a 与 a++
>

```javascript
如：a=2
++a------>先加加在给a---->(++a)+a--->//3+3
a++------>先不变化---->(a++)+a--->//2+3
```

> 按位与& 和 短路与&&
>

```javascript
&& 短路与   只要左侧为false,则右侧不参与运算.
console.log((a++)>2 && (a++))   ===>a++先未变化所以是2--->所以前边为假，后边不在看了
console.log(a)=====>结果为3
```

> 数据类型

```javascript
<!-- 
		    常用的数据类型:
			1.string--------var a='hello'
			2.number
			3.boolean
			4.object---------student={
									'name':'张三',
									'age':18
							 }
			5.undefined
			
			判断数据类型: 
			typeof(变量)  得到类型
		 -->
```

> 类型转化

```javascript
<!-- 
		  使用'+'的特点：
		  ''+5  ===>'5'
		  ''+true===>'true'  
		  9.99+'' ===>'9.99'
		  任何数据类型只要想变成字符串则可以通过'+'拼接
		 		  
		  string ---> int  float (number)
		  parseInt()
		  parseFloat()
		 -->

```

> 判断语句

```javascript
			var age = 10;
			if (age >= 18) {
				console.log('成年人')
			} else {
				console.log('未成年！')
			}
			/*python中
			 if 条件1:
				....
			 elif 条件2:
				....
			 else:
				....
			*/
			letter = 'F'
			switch (letter) {
				case 'A': 
					console.log('AAA')
					break
				default:
					console.log('default default default')
			}
```

> while循环语句

```javascript
			/*python中
			 a=1
			 while a<=10:
			 	print(a) 
				a=a+1
			*/
			var a=11;
			while(a<=10){
				document.write(a+'<br/>')
				a++;
			}
			var a = 11;
			do{
				document.write(a + '<br/>')
				a++;
			}while (a <= 10)----------------------->至少执行一次
```

> for循环

```javascript
			/*python中
			  for i in range(10):
			        print(i)
			*/
			for (i = 0;; i<10; i++) {
				console.log(i)
			}
			var foods=['馒头','米饭','窝窝头','大饼']   // 类似python list
			// for(index in foods){ 其中index就是下标  如果取值话则通过								foods[index]}
			for(f in foods){
				if(f==2){
					break------>结束循环---0,1
                  	continue---->结束本次循环---0,1,3
				}
				console.log(foods[f])
			}
```

#### 文本框取值

```javascript
			/*
			 python中函数的定义：
			 def 函数名(参数):
			     函数体 
			 js的函数定义:
			 function 函数名(参数){
				 函数体
			 }	
			*/
function caculate() {
	/*
	步骤：
		1.取值
			找对象： document.getElementById(id值)
			取值： input对象有value属性  对象.value
		2.转换
			parseInt()
		3.计算 +
		4.设置结果到div中
			找对象： document.getElementById(id值)
			设置值：双标签 没有value属性  innerText属性
				div对象.innerText=值
			样式的使用：mydiv对象.style.display='block' | 'none'
	*/
	first_input = document.getElementById('first').value
	second_input = document.getElementById('second').value
	if (first == '' || second == '') {
  		alert('必须输入值才可以运算！')
  		return;
	}
	result = parseInt(first) + parseInt(second)
	mydiv = document.getElementById('result')
	mydiv.innerText = '计算的结果是:'+result
	mydiv.style.display='block'
}
<input type="button" value="计算" onclick="caculate()">
```

#### 简易计算器

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>简易计算器</title>
		<style type="text/css">
			#div_total{
				width: 500px;
				height: 650px;
				border: 1px #D3D3D3 solid;
			}
			#div_top{
				width: 350px;
				height: 70px;
				background-color: white;
				border: 1px #D3D3D3 solid;
				margin: 15px 25px;
			}
			.div1{
				width: 400px;
				height: 100px;
				line-height: 100px;
				margin: 25px 50px;
			}
			.div_inner{
				width: 60px;
				height: 60px;
				background-color: white;
				margin: 20px;
				float: left;
				text-align: center;
				line-height: 60px;
				border: 1px #D3D3D3 solid;
			}
		</style>
		<script type="text/javascript">
			function result(val){
				console.log(val);
				var result = document.getElementById('div_top');
				switch (val){
					case '=' :
						result.value = eval(result.value);
						break;
					case '清除' :
						result.value = "";
						break;
					default:
						result.value += val
						console.log(result.value)
				}
			}
		</script>
	</head>
	<body>
		<div id="div_total">
			<div class="div1" style="margin-top: 0px;">
				<!-- <div id="div_top"></div> -->
				<input type="button" id="div_top" value="" />
			</div>
			<div class="div1">
				<input type="button" id="qinchu" value="清除" 									class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="add" value="+" class="div_inner" 							onclick="result(this.value)"/>
				<input type="button" id="sub" value="-" class="div_inner" 							onclick="result(this.value)"/>
				<input type="button" id="mul" value="*" class="div_inner" 							onclick="result(this.value)"/>
			</div>
			<div class="div1">
				<input type="button" id="num1" value="1" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num2" value="2" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num3" value="3" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="div" value="/" class="div_inner" 							onclick="result(this.value)"/>
			</div>
			<div class="div1">
				<input type="button" id="num4" value="4" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num5" value="5" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num6" value="6" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" value="=" class="div_inner" 								onclick="result(this.value)"/>
			</div>
			<div class="div1">
				<input type="button" id="num7" value="7" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num8" value="8" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num9" value="9" 										class="div_inner" onclick="result(this.value)"/>
				<input type="button" id="num0" value="0" 										class="div_inner" onclick="result(this.value)"/>
			</div>
		</div>
	</body>
</html>

```
## 第六天

### js

#### 验证码

```javascript


```



#### 下拉列表浏览足迹

```

```



#### window对象

```javascript
<!-- 
  		window对象：
		弹框: alert()  confirm()   prompt()可输入的对话框
		open()
		close()
		setInterval(动作，间隔时间)
-->
```

> window属性

```
console.log(window.outerWidth + "窗口的外部宽高" + 														window.outerHeight)
console.log(window.innerWidth + "窗口的文档显示区宽高" + 													window.innerHeight)
```

> window方法

```
			answer = window.confirm('确定要关闭窗口吗？')
			console.log(answer)  // true false
			if(answer){
				window.close()
			}
			
			function changeColor() {
				color = window.prompt('请输入颜色:')
				window.document.body.bgColor = color
			}
			
			function openWindow(){
				//打开新的窗口  类似超链接 target='__blank'		   				window.open('http://www.baidu.com/',
				 'baidu','height=800,width=1000,toolbar=yes,
				 menubar=yes,location=yes')
			}
```

![window方法](/window方法.PNG)

#### setInterval系统时间

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>setInterval系统时间</title>
		<style type="text/css">
			#mytime{
				width: 200px;
				height: 30px;
				border: 1px #000000 solid;
				line-height: 30px;
				text-align: center;
			}
		</style>
	</head>
	<body onload="changeTime()">
		<div id="mytime"></div>
		<script type="text/javascript">
			function changeTime(){
				document.getElementById('mytime').innerHTML = new Date().toLocaleString()
			}
			window.setInterval('changeTime()',1000)
		</script>
	</body>
</html>

```



#### setInterval轮播图

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>setInterval轮播图</title>
	</head>
	<body>
		<img src="../img/goods001.jpg" id="img">
		<script type="text/javascript">
			var i=1;
			function changeImg(){
				img = document.getElementById('img');
				img.src = '../img/goods00'+i+'.jpg';
				i++;
				if(i==4){
					i=1;
				}
			}
			setInterval('changeImg()',1000)
		</script>
	</body>
</html>

```









## 第七天

### JavaScript

#### setInterval轮播图

```

```



#### js小结

```
内置对象：

string

var name='abc'

name.charAt()

name.indexOf()  -1

name.substr(start,length)

name.substring(start,end)

正则表达式：

split  replace  search  match

正则表达式：

定义方式：

var patt = /^...$/igm   /\d+/gi

var patt = new RegExp('\d+','ig')

方法：

test()  exec()  compile()

Math对象：

Math.random()  

Math.abs()

Math.floor()

Math.ceil()

Math.round()

Math.sqrt()

Math.pow()

Date对象：

var date =new Date()

getFullYear()  2019

getMonth()

getDate()

...

toLocaleString()

Array对象：

定义：

var arr = Array()

var arr=[]

arr.length

arr.push()

arr.pop()

arr.concat()

arr.join()

arr.slice()

arr.splice()

arr.sort()

二维数组：var a = [ [] , [1,2,3] , [],...]

a1

自定义对象：

var student = {

    'name':'tom',
    'age':18,
    'friends':['lily','jack',..]

}



BOM模型：

window

弹出框：alert()   confirm()  prompt()

open() close()

setInterval()

clearInterval()

setTimeout()

clearTimeout()

```















## 第八天



### JavaScript

#### js总结

```
变量：

var 变量=10;

变量=10

数据类型： string number boolean  object  undefined

语法：  if...else

    	if ....else if ....else if ...else
    	switch...case
    	for
    	for ...in
    	while
    	do..while

函数+事件：

function 函数名(){

	

}

onclick='函数名()'

内置对象： string  Math  Date  Array  正则。。。

new Date() ---->当期的日期和时间

BOM模型：

window

    弹框： alert  confirm  prompt
    open  close
    
    f= setInterval(‘动作’,毫秒)  每隔
    clearInterval(f)
    
    setTimeout(‘动作’,毫秒)  只执行一次
    clearTimeout()

screen  history  location  navigator ...

DOM模型：

document.getElementById()

document.getElementsByName()

document.getElementsByTagName()

document.getElementsByClassName()

document.write()

document.querySelector('#aa>ul')  Node

document.querySelectorAll('#aa>ul')   NodeList

 nextElementSibling  下一个

 previousElementSibling 上一个

 children  孩子们

 parentElement  父节点

 添加：

 createElement('标签名')

 父元素.appendChild(新标签对象)

 父元素.insertBefore(新标签对象,参照对象)

 删除：

 父元素.removeChild(要删除的元素)

事件：

标签：

<button onclick='show()' id='btn'>点击</button>

js:

document.getElementById('btn').onclick=function(){

	

}

种类：

onmouseover

onmouseout

onclick

onmousedown

onmouseup

onload

onchange

onblur 失去焦点

onfocus 获取焦点



jquery:








```

#### 结点

```

```



### 

#### 购物车

```javascript

```

### jquery











## 第九天

### jquery

#### 选择器

```
$('div:contains(again)')// 根据内容进行筛选
$('div:empty') //内容为空的div
$('div:has(p)') // 里面含有p选择器 的div
$('tr:visible') // 所有可见行-----$("tr:hidden")//查找隐藏的 tr
$('input[type="text"]').css('color','red')
$('input[name="accept"]').val()//// jquery取值: val()  
// html() ~ innerHTML   text() ~ innerText



```



#### 轮播图

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style type="text/css">
			#container{
				width: 180px;
				margin: 0 auto;
				position: relative;
			}
			ul{
				list-style: none;
				position: absolute;
				bottom: 0px;
				padding-left: 0px;
			}
			li{
				float: left;
				width: 10px;
				height: 10px;
				background-color: transparent;
				border-radius: 50%;
				margin-left: 25px;
				border: 2px darkgray solid;
			}
			span{
				display: inline-block;
				width: 40px;
				height: 40px;
				text-align: center;
				line-height: 40px;
				font-size: 25px;
				color: darkgray;
				background-color: #FAEBD7;
				position: absolute;
				top: 50px;
				cursor: default;
				opacity: 0.5;
			}
			#left{
				left: 0px;
				
			}
			#right{
				right: 0px;
			}
			span:hover{
				background-color: #000000;
			}
			.selected{
				background-color: #FAEBD7;
			}
		</style>
		<script src="https://cdn.bootcss.com/jquery/2.2.3/jquery.min.js"></script>
		
	</head>
	<body>
		<div id="container">
			<img src="../img/goods001.jpg" id="pic">
			<ul>
				<li></li>
				<li></li>
				<li></li>
			</ul>
			<span id="left">&lt;</span>
			<span id="right">&gt;</span>
		</div>
		<script type="text/javascript">
			f = setInterval('lunbo()',1000)
			n = 1;
			lis = $('#container ul li')
			function lunbo(){
				$('#container img').attr('src','../img/goods00'+n+'.jpg')
				lis.removeClass('selected')
				lis.eq(n-1).addClass('selected')
				n++
				if(n==4){
					n = 1
				}
			}
			lis.each(function(i){
				lis.eq(i).hover(function(){
					clearInterval(f)
					$('#container img').attr('src','../img/goods00'+(i+1)+'.jpg')
					lis.removeClass('selected')
					// lis.eq(i).addClass('selected')
					$(this).addClass('selected')
				
				},function(){
					f = setInterval('lunbo()',1000)
				})
			})
		</script>
	</body>
</html>

```



#### 留言板

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>留言板</title>
		<script type="text/javascript" src="js/jquery-3.3.1.js"></script>
		<style>
			#container{
				width: 70%;
				height: 400px;
				overflow: auto;
				border: 1px solid lightgray;
			}
			
			#div1{
				margin-top: 50px;
			}
			
			textarea{
				width: 50%;
				height: 100px;
				border: 1px solid gray;
				font-size: 18px;
			}
			
			div p{
				position: relative;
				margin-left: 10px;
				padding-bottom: 10px;
				border-bottom: 1px solid #D3D3D3;
			}
			
			div p span{
				position: absolute;
				font-size: 12px;
				right: 0px;
				color: #D3D3D3;
				margin-right: 10px;
			}
			
		</style>
	</head>
	<body>
		<div id="container">
			<p> dhfjdhf  <span></span></p>

		</div>
		<div id="div1">
			<form>
				评论:<br />
				<input type="text" id="username"/>
				<br /><br />
				<textarea id="content"></textarea>
				<br />
				<input type="button" value="评论" id="btn" />
			</form>
		</div>
		<script type="text/javascript">
			$('#btn').click(function() {
				comment = $('#content').val()
				username =$('#username').val()
				if(comment==''||username==''){
					alert('必须输入用户名或者评论！')
					return
				}
				content ='<p>'+username+'<br/>'+comment+' <span>'+new Date().toLocaleString()+'</span></p>'
				$('#container').prepend(content)
				//清空
				$('#content').val('')
				$('#username').val('')
			})
		</script>
	</body>
</html>
```





## 第十天

### jquery

#### 工具

```javascript
1、
//jQuery.each(object, [callback])
//$.each()是对数组，json和dom结构等的遍历
	object:需要遍历的对象或数组。
	callback:每个成员/元素执行的回调函数
//--------$.each(arr1,function(i,val){ //两个参数，第一个参数表示遍历的数组的下标，第二个参数表示下标对应的值
/*--------$.each( { name: "John", lang: "JS" }, function(key, value){
  alert( "Name: " + key + ", Value: " + value );
});*/
/*-------var lis =$('li')
		 $.each(lis, function(i, n) {
			console.log("Item #" + i + ": " + n);  /i是下标，n是li的对象1
			n.innerText=i   //javascript
			// $(n).text(i) //jquery向页面写入
		 });*/
2、
$("input:hidden").each(function(i,val){  //第一个参数表示索引下标，第二个参数表示当前索引元素
    alert(i);
    alert(val.name);
    alert(val.value);       
});
lis.each(function(i){
	$(this).text(i)
})

```

#### 事件

```javascript
1、页面加载事件：
      当DOM载入就绪可以查询及操纵时绑定一个要执行的函数。
      $(document).ready(function(){
            $('div').append('<img src="img/studio_0001.jpg"/>')
      })
      简写形式：
      $(function($) {
  		// 你可以在这里继续使用$作为别名...
	  });
2、绑定事件
	//javascript的点击事件$('#mydiv').click(function(){})
	//jquery
	$('#mydiv').on('click',function(){
		$(this).css('background-color','yellow')
	})
	//javascript的触发事件$('#mydiv').hover(function(){},function(){})
	//jquery
	$('#mydiv').on({
      			 mouseover: function() {
					$(this).css('background-color', 'yellow')
				},
				mouseout: function() {
					$(this).css('background-color', 'blue')
				}
			})
```

#### 列表模糊查询

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>作业</title>
		<script type="text/javascript" src="js/jquery-3.3.1.js"></script>
		<style type="text/css">
			#container {
				width: 300px;
				border: 1px solid #333;

			}
			#top {
				background-color: darkgray;
				padding: 10px;
				/* text-align: center; */
			}
			#search {
				width: 200px;
				height: 25px;
				border-radius: 8px;
			}
			ul{
				padding-left: 0px;
			}	
			li{
				list-style: none;
				border-bottom: 1px solid lightgray;
				margin-top: 10px;
				margin-bottom: 10px;
				padding-bottom: 10px;		
			}
			li span{
				margin-left: 20px;
			}
		</style>
	</head>
	<body>
		<div id="container">
			<div id="top">
				<p>搜索列表内容:</p>
				<input type="text" id="search">
			</div>
			<div id="bottom">
				<ul>
				</ul>
			</div>
		</div>
		<script type="text/javascript">
			contents = ['aaa', 'abc', 'apple', 'jquery', 'javascript', 'java', 'push', 'bed', 'bread', 'browser', 'jack',
				'search', 'password','bottom','AAA','AB','ABC','ABB'
			]
			$(function(){
				for(var i=0;i<contents.length;i++){
					$('ul').append('<li><span>'+contents[i]+'</span></li>')
				}
			})
			$('#search').keyup(function(){//按键抬起事件
				//清空ul
				$('ul').empty()
				var v= $(this).val()  // ab
				var arr=[]  // 存放匹配元素
				var regexp =new RegExp('^'+v,'i')
				for(var i=0;i<contents.length;i++){
					if(regexp.test(contents[i])){
						arr.push(contents[i])
					}
				}
				//找到所有匹配的元素
				for(var i=0;i<arr.length;i++){
					$('ul').append('<li><span>'+arr[i]+'</span></li>')
				}
			})
		</script>
	</body>
</html>
```

#### Ajax

```javascript
1、
//jQuery.ajax(url,[settings])
$.ajax({
  	url:'http://localhost/post111.php',  //发送请求的地址
	type:'POST',  //请求方式（post或get）默认为get
	data:{name:name,content:content},//发送到服务器的数据
	dataType:'json',  //预期服务器返回的数据类型
	success:function(data){   // 请求成功之后返回的json数据.
      //data表示的就是服务器返回的json格式的数据
      //json数据格式是：data：{username:值,conetent:值}
		if(data.status==200){
			msg ="<p>" +data.username+"</p>"
			$('#container').append(msg)
		} 						
	},
	error:function(data) {  //请求失败时被调用的函数
		alert('失败')
	}
})
2、
//jQuery.post(url, [data], [callback], [type])
	url:发送请求地址。
	data:待发送 Key/value 参数。
	callback:发送成功时回调函数。
	type:返回内容格式，xml, html, script, json, text, _default。
$.post('http://localhost/post111.php', 		                		   {username:username,content: content},
       function(data) {   //data的数据string类型
  					//可用data = JSON.parse(data)转成JSON类型
		if (data.status == 200) {
			msg = "<p>" + data.username +"</p>"
			$('#container').append(msg)
		}
	  }, 'json')
3、
//jQuery.getJSON(url, [data], [callback])
	url:发送请求地址。
	data:待发送 Key/value 参数。
	callback:载入成功时回调函数。
    
$.getJSON('http://localhost/get111.php', 
          {username: username,content: content}, 
          function(data) {  //请求成功之后返回的json数据
			if (data.status == 200) {
				msg = "<p>" + data.username  + "</p>"
				$('#container').append(msg)
			}
		})
```



##### Ajax案例

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Post格式的ajax请求</title>
		<script type="text/javascript" src="js/jquery-3.3.1.js"></script>
		<style type="text/css">
			#username {
				width: 200px;
				height: 25px;
				border: 1px solid #D3D3D3;
				margin: 10px;
			}

			textarea {
				width: 40%;
				height: 50px;
				border: 1px solid #333;
				font-size: 16px;
				margin: 10px;
			}
		</style>
	</head>
	<body>
		<form>
			发表评论:<br />
			<input type="text" name="username" id="username" /><br>
			<textarea id="content"></textarea>
			<br>
			<input type="button" value="发表评论">
		</form>
		<div id="container"></div>

		<script type="text/javascript">
			$(':button:first').click(function() {
				//取值
				var username = $('#username').val()
				var content = $('#content').val()
				if (username == '' || content == '') {
					alert('内容不能为空！')
					return
				}
				//使用ajax发送请求
				// 	$.ajax({
				// 		type:'POST',
				// 		url:'http://localhost/post111.php',
				// 		data:{
				// 			username: username,
				// 			content: content
				// 		},
				// 		dataType:'json',
				// 		success:function(data){   // 请求成功之后返回的json数据.
				// 			if(data.status==200){
				// 				msg ="<p>" +data.username+"发表的内容是:"+data.content+"</p>"
				// 				$('#container').append(msg)
				// 			} 						
				// 		}
				// 	})
          
				//简化版  getJSON(url,data,fn)
				// 	$.getJSON('http://localhost/get111.php', {
				// 		username: username,
				// 		content: content
				// 	}, function(data) {
				// 		if (data.status == 200) {
				// 			msg = "<p>" + data.username  + "</p>"
				// 			$('#container').append(msg)
				// 		}
				// 	})

				//使用简化版的post方式
				$.post('http://localhost/post111.php', {
					username: username,
					content: content
				}, function(data) {
		//真实的JSON  {"username":"admin123","content":"q2w3e4r5t6","status":"200"}
                  		console.log(data)
					// 	result = JSON.parse(data)   // 转成对象
					// 	console.log(result)
					// 	if (result.status == 200) {
					// 		msg = "<p>" + result.username + "</p>"
					// 		$('#container').append(msg)
					// 	}
					if (data.status == 200) {
						msg = "<p>" + data.username + "发表的内容是:" + data.content + "</p>"
						$('#container').append(msg)
					}
				}, 'json')
			})
		</script>
	</body>
</html>

```



```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>获取新闻</title>
		<script type="text/javascript" src="js/jquery-3.3.1.js"></script>
	</head>
	<body>
		<button>获取新闻信息</button>
		<ul id="news"></ul>
		<script type="text/javascript">
			var $ul=$('#news')
			$('button').click(function(){							        $.getJSON('http://localhost/newsList.php',
                     function(data){
					for(var i=0;i<data.length;i++){
// {title: "德国女总理默克尔滑雪时摔倒 骨盆断裂", date: "2014-1-6"}
					  content = '<li>'+data[i].title+"-----"+data[i].date+"</li>"
					  $ul.append(content)
					}	
				})
			})
		</script>
	</body>
</html>

```







































