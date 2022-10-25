### 你大概需要3min来阅读这篇文章

这里是Feishiko，今天来分享一下关于如何在GMS2中实现时间缓动的效果。

这个效果本身实现起来不难，所以这边主要是来点一下思路。

## 图像绘制

个人比较懒，所以就直接画出来了

oPlayer DrawEvent

```
draw_circle_color(x, y, 16, c_red, c_red, false);//绘制一个实心红球
```

oBullet DrawEvent

```
draw_circle_color(x, y, 5, c_blue, c_blue, false);//绘制一个实心蓝球
```

## 准备工作

接下来点一下要怎么实现，首先子弹和玩家都会有一个速度，当时间减慢的时候，玩家的速度和子弹的速度都会变慢，所以我们要用他们的速度除以一个>1的数，或者乘以一个小数。

首先玩家和子弹都需要一个速度，我这边都记为spd变量，然后让他们除以一个全局变量，如果你不想用全局变量也可设置一个object保持，假设是oGameCont，那就oGameCont.那个变量，这个是控制全局物体速度的核心变量。

具体实现起来像这个样子。

```
var realSpeed = spd/global.gearTimes;
```

于是我们得到了计算之后真正的**速度**

## 核心代码

接下来如何让角色移动，子弹移动，都采用这个计算出来所得到的速度。

这是玩家移动的大致代码

```
if(keyboard_check(vk_up) && keyboard_check(vk_right)){
	x += lengthdir_x(realSpeed, 45);
	y += lengthdir_y(realSpeed, 45);	
}else if(keyboard_check(vk_up) && keyboard_check(vk_left)){
	x += lengthdir_x(realSpeed, 135);
	y += lengthdir_y(realSpeed, 135);	
}else if(keyboard_check(vk_left) && keyboard_check(vk_down)){
	x += lengthdir_x(realSpeed, 180 + 45);
	y += lengthdir_y(realSpeed, 180 + 45);	
}else if(keyboard_check(vk_right) && keyboard_check(vk_down)){
	x += lengthdir_x(realSpeed, 270 + 45);
	y += lengthdir_y(realSpeed, 270 + 45);	
}else if(keyboard_check(vk_up)){
	x += lengthdir_x(realSpeed, 90);
	y += lengthdir_y(realSpeed, 90);	
}else if(keyboard_check(vk_down)){
	x += lengthdir_x(realSpeed, 270);
	y += lengthdir_y(realSpeed, 270);	
}else if(keyboard_check(vk_left)){
	x += lengthdir_x(realSpeed, 180);
	y += lengthdir_y(realSpeed, 180);	
}else if(keyboard_check(vk_right)){
	x += lengthdir_x(realSpeed, 0);
	y += lengthdir_y(realSpeed, 0);	
}
```

*完美移动*

虽然会繁琐一点，但是这样移动不会出现斜向更快的现象。

子弹的移动代码

```
x += lengthdir_x(realSpeed, direction);
y += lengthdir_y(realSpeed, direction);
```

之所以运用这种方法而不用GMS自带的变量是因为这样会更好更方便操纵，也会更好的管理。当然视具体情况而定，有时候也可以小用一下GMS的内置变量，比如我照样用这里的direction。

时缓和正常状态，我这里用了一个比较丝滑的方法过渡。

```
if(keyboard_check(vk_shift)){
	global.gearTimes = lerp(global.gearTimes, 5, .05);	
}else{
	global.gearTimes = lerp(global.gearTimes, 1., .05);	
}
```

*线性插值*

## 最后效果
![演示效果](https://img-blog.csdnimg.cn/96453f8ec12349acaed8f1958a5cf0e2.gif#pic_center)
大概就是这么多，希望你喜欢本期内容！

个人itch.io链接[点这里](https://feishiko.itch.io/)
个人Twitter链接[点这里](https://twitter.com/FeishikoMonster)

2022/10/15