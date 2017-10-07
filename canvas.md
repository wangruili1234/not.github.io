# canvas

### 1 canvas的简介

##### 	1-1 canvas是h5新增的标签,,默认宽高为300×150像素;

##### 	1-2 写在canvas中的文字一般不会显示出来,一般不显示,通常用于做浏览器兼容性的提示;

##### 	1-3 可以设置canvas标签的大小,建议使用js或者html的属性设置宽高;如果给canvas用CSS设置宽高,画布内的内容随画布的变化而变化;

##### 	1-4 canvas标签,只是标签而已,自身并不具备绘图的能力;

### 2 canvas的使用

```JavaScript
2-1 获取canvas标签
2-2 获取2d绘图的API
	var ctx=canvas标签.getContext('2d');//webgl(3d绘图API)
2-3绘制;
	lineWidth//设置线条的宽度;
	ctx.moveTo(100,100);//移动画笔(线的起点)
	ctx.lineTo(200,100);//画线(线的终点)
	ctx.stroke();//绘制 描边
	ctx.stokeStyle='';//描边的样式
	ctx.closePath();//将起点和终点进行连线,闭合路径
	ctx.fill();//填充(如果路径没有闭合,会自动闭合再填充);满足非零环绕数原则;
	ctx.fillStyle='';//填充的样式;
//注意:moveTo只是移动画笔不画线;lineTo移动画笔并且画线;
```

### 3 非零环绕原则

```
从该区域中引出一条线,这条线和边界的相交结果不为零就填充,为零不填充;             
```

### 4 路径的概念

路径就是一次绘图;

```javascript
ctx.beginPath()//开启一个新的路径
```

### 5 线型相关属性

```JavaScript
5-1 lineWidth//线宽
5-2 lineCap//线末端类型
	butt//表示两端使用方形结束;默认值;
    round//表示两端使用突出的圆角结束;
    square//表示两端使用突出的方形结束;
5-2 lineJoin//设置相交线拐点
	round//使用圆角连接
    bevel//使用平切连接
    miter//使用尖角连接,默认值
```

### 6 虚线

```JavaScript
6-1 getLineDash();用于获取虚线//获取的值是数组的形式
6-2 setLineDash([]);用于设置虚线
6-3 innerDashOffset=number;设置虚线偏移,用于微调(正直向左,负值向右)
```

### 7 内置画矩形的api

7-1 设置一个矩形

cxt.rect(起点x轴坐标,起点y轴坐标,宽,高);

7-2 绘制一个描边矩形,不会产生任何路径

cxt.strokeRect(起点x轴坐标,起点y轴坐标,宽,高);

7-3 绘制一个填充矩形,不会产生任何路径

cxt.fillRect(起点x轴坐标,起点y轴坐标,宽,高);

### 8 清除画布

按照矩形的大小来清除画布指定位置的内容

cxt.clearRect(起点x轴坐标,起点y轴坐标,宽,高);

canvas.width//获取画布宽度

canvas.height//获取画布高度

### 9 画布的状态保存和恢复

```JavaScript
cxt.save()//保存当前画布状态;
cxt.restore()//恢复(第一次恢复到最近一次的保存状态);

```

### 10 绘制圆弧

```JavaScript
cxt.arc(x,y,radius,startAngle,endAngle,falg);
//cxt.arc(圆心x坐标,圆心y坐标,半径,起始的弧度,结束的弧度,是否逆时针);
//弧度/2Math.PI=角度/360;
//弧度=角度*Math.PI/180;
//注意点:
//1 使用 arc 绘图的时候, 如果没有设置 moveTo 那么会从开始的绘弧的地方作为起始点. 如果设置了 moveTo, 那么会连线该点与圆弧的起点.
//2 如果使用 stroke 方法, 那么会从开始连线到圆弧的起始位置. 如果是 fill 方法, 会自动闭合路径填充.
arcTO(x1,y1,x2,y2,radius)//方法使用使用切点和一个半径，来为当前子路径添加一条圆弧。
//x1,y1 点p1的坐标
//x2,y2 点p2的坐标
//定义圆弧的圆的半径;
```

### 11 绘制文字

```JavaScript
cxt.fillText(str,x,y)//填充文字
//cxt.fillText(文字,x坐标,y坐标,最大宽度)
cxt.strokeText()//描边的文字
//cxt.strokeText(文字,x坐标,y坐标,最大宽度)
cxt.font=''//设置文字,语法同css;
cxt.measureText(文字)//测量文字,返回的结果是对象
```

### 12 绘制图片

```JavaScript
绘制图片的方法:drawImage;
drawImage(img,dx,dy);
drawImage(img,dx,dy,w,h);
drawImage(img,x,y,w,h,dx,dy,dw,dh);//(x,y,w,h :要截取原图的部分;dx,dy,dw,dh:要绘制图片的宽高和位置即在canvas中的位置及大小);
//img:要绘制canvas中的图片
//dx:画在canvas中的x坐标
//dy:画在canvas中的y坐标
//w:要绘制的宽度
//h:要绘制的高度
//注意:图片加载完成之后再绘制图片
```

### 13 变换

#### $$ canvas 所有变换都是针对的坐标系

```javascript
平移  canvas.translate(x,y);//x为正向右,y为正向下;
旋转  canvas.rotate(a)//参数是弧度,正值顺时针,负值逆时针
//角度*Math.PI/180=弧度;
缩放  canvas.scale(x,y)//传入坐标系放缩的参数,值大于1放大,小于1缩小;坐标值取-1,坐标轴反向;
```

