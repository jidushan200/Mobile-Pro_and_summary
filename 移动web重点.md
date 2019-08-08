##渐变
###   1.线性渐变

```css
background-image: linear-gradient()
backgroound:linear-gradient()
/* 
  渐变的方向：to 和方位名称或者用角度来表示
  to right
  to left 
  to top
  to bottom
*/
/* 注意点:用角度表示方位时，0度表示从下向上，90度表示从左向右 */
/* 语法：*/
background-image：linear-gradient(
  to right,
  red,
  blue
)
```
###  2.径向渐变
```css
   /*background-image:radial-gradient()
   确定渐变的原点位置
   关键字 at
   例如： at 方位名称 at center  at right top

          at  值    at 100px 100px
          */
   /*语法：*/
      background-iamge:radial-gradient(
         200px 100px at center,
         <!-- 开始颜色 -->
         red,
         <!-- 结束颜色 -->
         blue
      )
```
##2d转化（transform复合属性）
###   1.位移translate改变元素位置

 语法：transform:translate(水平位置，垂直位置)
  示例：定位盒子实现居中显示（2d）
```html
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
    
    *{
        margin: 0;
        padding: 0;
    }
    .father{
        width: 300px;
        height: 300px;
        background-color: red;
        position: relative;
    }
    .son{
        width: 100px;
        height: 100px;
        background-color: pink;
        position: absolute;
        left: 50%;
        top:50%;
        transform: translate(-50%,-50%);
    }
    </style>
</head>
<body>
    <div class="father">
        <div class="son"></div>
    </div>
</body>
</html>
      
```

###   2.旋转rotate

    语法：transform：rotate（度数）
    改变轴心点的位置
    transform-origin: 水平值 垂直值
###   3.scale缩放

    语法：transform：scale(0,0)
    注意：设置值时不能带单位，值代表的是倍数
          第一个值示宽度的倍数，第二个值表示高度的倍数
          放大值大于1 缩小值小于1
###   4.倾斜skew

    语法：
    transformL:skew(水平倾斜度，垂直倾斜度)
    注意：只设置一个值表示沿水平方向倾斜
##3d转化（transform复合属性）
  3d的坐标轴有三个轴：
      X轴（水平）从左向右为正方向
      Y轴（垂直）从上向下为正方向
      Z轴 从里向外为正方向
###    1.位移translate

     语法：
    transform: translateX() translateY() translateZ()
       示例：定位盒子实现居中显示（3d）
```html
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
    
    *{
        margin: 0;
        padding: 0;
    }
    .father{
        width: 300px;
        height: 300px;
        background-color: red;
        position: relative;
    }
    .son{
        width: 100px;
        height: 100px;
        background-color: pink;
        position: absolute;
        left: 50%;
        top:50%;
        transform:translateX(-50%) translateY(-50%);
    }
    </style>
</head>
<body>
    <div class="father">
        <div class="son"></div>
    </div>
</body>
</html>
      
```
   注意：在网页中如果想实现近大远小的效果需要添加透视
         perspective 值建议取值600px-1000px,需要加在
         设置了transf属性的父元素身上
###    2.旋转rotate（）

     语法：transform：rotateX() rotateY() rotateZ()
###    3.缩放scale（）

    语法：transform：scaleX（） scaleY() scaleZ()
###    4.倾斜skew（）

     语法：transform：skewX（）
 ##动画anmiation
###    1.定义动画序列

      关键字@keyframes 动画名{
          from{
              设置动画开始说状态的代码
          }
          to{
              设置动画结束的代码
          }
      }
###    2.动画的相关属性：

     2.1动画名：animation-name:
     2.2动画执行时间：animation-duration:
     2.3动画执行次数：animation-iteration-count: 默认值为1
     infinite表示无限次
     2.4动画逆播：animation-direction:alternate
     2.5动画速度类型：animation-timing-function:linear
     2.6动画结束时候的状态animation-fill-mode:forwards;
     2.7动画延时animation-delay:1s
     2.8动画播放animation-play-state:paused
### 动画相关属性分写示例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
    *{
        margin: 0;
        padding: 0;
    }
    .box{
        width: 200px;
        height: 200px;
        background-color: pink;
        /* 动画名 */
        animation-name: move;
        /* 动画逆播 */
        animation-direction:alternate;
        /* 动画执行次数 */
        animation-iteration-count: infinite;
        /* 动画执行时间 */
        animation-duration: 2s;
        /* 动画延时 */
        animation-delay: 1s;
        /* 动画执行的状态 */
        animation-timing-function: linear;
        
    }
    .box:hover{
        animation-play-state: paused;
    }
    @keyframes move{
        form{
            transform: translateX(0px);
        }
        to{
            transform: translateX(500px)
        }
    }
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```
### 动画合写示例

```html
 <!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		.box {
			width: 200px;
			height: 200px;
			background-color: red;
			position: relative;

			/* 合写 */
			animation: alternate  1s infinite  linear  1s  change;
		}

		@keyframes change {
			from {
				left: 0;
			}
			to {
			  left: 500px;
			}
		}
	</style>
</head>
<body>

	<div class="box"></div>
	
</body>
</html>
```
### 动画多状态写法示例

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style type="text/css">
		* {
			margin: 0;
			padding: 0;
		}

		.box {
			width: 200px;
			height: 200px;
			background-color:red;
			margin: 150px auto;


			animation: change1 10s linear;
		}


		@keyframes change1 {
			0% {
				width: 200px;
			}

			50% {
				width: 400px;
				height: 200px;
			}

			100% {
				width: 400px;
				height: 400px;
			}
			
			80% {
				width: 400px;
				height: 400px;
				background-color: red;
			}

			100% {
				width: 400px;
				height: 400px;
				background-color: blue;
			}
	

		}
	</style>
</head>
<body>
	 <div class="box"></div>
</body>
</html>
```
##视口viewport
```html
<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
```
###   1.视口相关属性

  width=device-width：表示的是设置宽度与当前设备一样宽
  initial-scale:禁止页面出现缩放效果
  user-scalable=no：禁止用户手动缩放

##伸缩布局(弹性布局)
  设置伸缩布局的步骤
  先给父元素设置伸缩盒子：display:flex;
  伸缩盒子相关属性：

###   1.设置主轴方向

    flex-direction:row(水平显示) column(垂直)
###   2.设置主轴对齐方式：

    justif-content：flex-start flex-end(结束位置) center(居中) space-around(环绕)space-between(两边对齐中间环绕 )
###   3.设置侧轴对齐方式：

    align-items：syuatch(拉伸) flex-start(结束位置)
    center(居中)
###   4.元素换行显示

    flex-wrap:wrap(换行) nowrap（不换行）
###   5.设置子元素独立对齐方式

    align-self:auto flex-start flex-end center baseline stretch
    伸缩布局示例
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>

	<style>
		.box {
			width: 500px;
			height: 600px;
			border: 1px solid red;
			margin: 100px auto;
			/* 设置为伸缩盒子 */
			display: flex;

			/* 设置主轴方向 */
			flex-direction: row;

			/* 设置主轴方向的对齐方式 */
			justify-content: flex-start;

			/* 设置侧轴对齐方式 */
			align-items: stretch;


			/* 设置元素是否换行显示 */
			flex-wrap: wrap; 

			
			/* 换行后的对齐方式 */
			align-content: stretch;
		}

		.one {
			width: 100px;
			height: 100px;
			background-color: blue;
			margin: 1px;
		}
	</style>
</head>
<body>
	<div class="box">
		<div class="one">1</div>
		<div class="one">2</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
		<div class="one">3</div>
	</div>
</body>
</html>
```
##rem适配
rem：相对单位，相对网页根标签（html）的文字大小
em：相对单位相对当前的标签文字大小
##媒体查询
媒体查询的步骤：

### 1.通过媒体查询方式（将设备分为若干份以20分为例，然后设置html的文字大小）

媒体查询语法：
@media only screen and(设备宽){

    html{
        font-size:设备宽/份数
    }
}
媒体查询示例
```less
@f:20;
// 适配320
@media only screen and(width:320px){
    html{
        font-size: 320px/@f;
    }
}
//适配360
@media only screen and(width:360px){
    html{
        font-size: 360px/@f;
    }
}
//适配375
@media only screen and(width:375px){
    html{
        font-size: 375px/@f;
    }
}
//适配414
@media only screen and(width:414px){
    html{
        font-size: 414px/@f;
    }
}
//适配768
@media only screen and(width:768px){
    html{
        font-size: 768px/@f;
    }
}
//适配1024
@media only screen and(width:1024px){
    html{
        font-size: 1024px/@f;
    }
}

```
##bootstrap Ui框架
###1.使用bootstrap步骤
必须引用bootstrap.css 的文件
###2.兼容ie版本
```html
<!-- [IF lt IE 9] -->
	<!-- html5shiv.js 解决标签不兼容 -->
	<!-- respond.js  解决 @media 不兼容 -->
<!-- [end] -->
```
###3.栅格布局
作用：实现响应式布局
栅格参数：
超小屏<768px      .col-xs-值 适配手机端
小屏>=768px       .col-sm-值 适配平板
中等屏>=992px     .col-md-值 适配桌面
超大屏>1200px     .col-lg-值 适配超大屏

在栅格布局下会将设备默认分为12等份

###1.使用栅格布局必须给父元素设置类名container 或者 container-fluid
栅格布局示例：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <link rel="stylesheet" href="bootstrap/css/bootstrap.css">
    <style>
    .box{
        height: 500px;
        background-color: red;
    }
    .item{
        height: 50px;
        border: 1px solid #ccc;
    }
    </style>
</head>
<body>
    <div class="container">
        <div class="item col-md-4 col-sm-6 col-xs-12">1</div>
        <div class="item col-md-4 col-sm-6 col-xs-12">2</div>
        <div class="item col-md-4 col-sm-12 col-xs-12">3</div>
    </div>
</body>
</html>
```
#