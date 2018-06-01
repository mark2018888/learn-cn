
> 不想自己亲手喂鱼? 这里刚好有一个适合你的micro:bit项目。在这篇文章中，我们将通过ADKeypad控制舵机的运动来喂鱼。

## 项目简介    
---

![](https://i.imgur.com/QO4eC0H.png)  

在这个项目中，我们将会制作一个喂鱼器。我们用ADKeypad上面的2个红色按钮来控制舵机的转动，并通过OLED屏幕上显示的信息得知舵机的状态。    

## 所需材料： 
---
- 1 x [BBC micro:bit](http://www.elecfreaks.com/estore/micro-bit-board.html)  
- 1 x USB线  
- 1 x [扩展板](http://www.elecfreaks.com/estore/elecfreaks-micro-bit-breakout-board.html)  
- 1 x [ADKeypad](https://www.elecfreaks.com/estore/octopus-adkeypad.html)  
- 1 x [OLED](https://www.elecfreaks.com/estore/iic-oled.html)  
- 1 x 舵机  
- 线  

**温馨提示: 如果你想要以上所有这些元器件，你可以购买我们的[micro:bit小小发明家套件](https://item.taobao.com/item.htm?spm=a230r.7195193.1997079397.9.z3IMPf&id=564707672256&abbucket=5)。**


## 目标：  
---
- 认识ADKeypad、OLED和舵机
- 用舵机来进行创造
- 用OLED来进行创造


## 制作过程  
---
### 步骤 1 – 元器件连接  

![](https://i.imgur.com/FNUJhZ3.jpg)
![](https://i.imgur.com/BAovMFM.jpg)

如上图所示，将micro:bit插入扩展板，并连接USB线，然后再插入OLED。你可以把OLED插入扩展板上3排排针插孔的任意一排。
将ADKeypad连接到扩展板上的引脚P0，把舵机连接到 Pin 1。确保线的颜色和扩展板上的引脚的颜色一致。

![](https://i.imgur.com/FHD6oh8.jpg)


### 步骤 2 – 编程前的准备  

我们将添加一个代码库来方便我们使用套件中的元器件。点击代码抽屉中的Advanced来查看更多代码选项，并在底部找到Add Package（添加代码库）。 

![](https://i.imgur.com/TF3bfdq.jpg)

这时将会弹出一个对话框。在对话框中，搜索“tinker kit"，然后点击下载这个代码库。

![](https://i.imgur.com/nOIgk5u.png)

注意：如果你收到提示说一些代码库因为不兼容的问题将被删除，你可以选择根据提示操作，或者在项目文件的菜单中选择新建一个新项目。


### 步骤 3 – 编程  

![](https://i.imgur.com/qLksxfG.jpg)

点击代码抽屉中的Tinkercademy， 找到与我们套件对应的积木块。

![](https://i.imgur.com/6CUN5SW.jpg)

你需要在开始的时候初始化OLED。64和128分别代表了OLED的长度和宽度。

![](https://i.imgur.com/gRJsbmX.jpg)

因为这里只有2个条件，所以我们只需要一个“else-if”语句。
如果ADKeypad上的按钮A被按下，舵机将会旋转至70度，OLED上将会显示“Loading food”（加载食物）。 
或者，如果ADKeypad上的按钮B被按下，舵机将会转至20度，OLED上将会显示“Feeding the fish”（喂鱼）。
你可以根据你的需要来调节舵机的角度。

如果你不想自己亲手编写代码，你可以通过下面这个链接下载程序的完整代码：

[https://makecode.microbit.org/_Azc57HcdM7r1](https://makecode.microbit.org/_Azc57HcdM7r1)

或者，你可以从下面这个页面下载：

<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/#pub:_Azc57HcdM7r1" frameborder="0" sandbox="allow-popups allow-forms allow-scripts allow-same-origin"></iframe></div>


### 步骤 4 – 成功!  

太棒啦！你已经制作好了一个喂鱼器哦!