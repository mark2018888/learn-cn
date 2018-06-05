还记得在老式的诺基亚手机上玩的贪吃蛇游戏吗？ 这款在5*5像素屏幕上的贪吃蛇游戏不但非常容易制作，而且还非常好玩哦！  

## 制作目标
---

在这篇手把手指导的制作说明中，我们将从零开始创建一个贪吃蛇游戏，操作控制按键，控制蛇的运动，设置输赢条件，以及绘制游戏面板。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/1-3.gif)

## 制作材料
---

- 1 x [BBC micro:bit](http://www.elecfreaks.com/estore/micro-bit-board.html)
- 1 x USB线
- 1x 耐心 (编程大概需要30 min)

**温馨提示: 如果你想要以上所有这些元器件，你可以购买我们的[micro:bit小小发明家套件](https://item.taobao.com/item.htm?spm=a230r.7195193.1997079397.9.z3IMPf&id=564707672256&abbucket=5)。**


###为什么选择Python?

- 读起来和英文一样 – Python是一种最简单的编程语言，这使它成为了初学者入门的最佳选择。 

- 灵活多变 – Python成为行业编程语言是有它的原因的。你可以用它来做很多东西。这也是为什么谷歌和Youtube用这门语言作为它们的后台支持语言。

- 社区活跃 – Python是初学者最受欢迎的编程语言之一。在它的社区有数不清的资源和帮助。这些帮助是非常有价值的。它不仅限于帮助你查看你的代码，它还可以帮助你扫除编程学习之路上的绊脚石。

- 实际编程比基于积木块拖拽式的编程看起来看更酷。我知道这看起来似乎特别深奥，但是看看这些颜色吧！


## 如何用Python开始编程?
---

如果你刚刚学习编程，你可能还没有Python编辑器。别担心! 你可以去到[Micro:bit官方的Python编辑器](http://www.python.microbit.org/)或者是下载离线版的Python编辑器[mu](https://codewith.mu/)来编写代码并发送代码到你的micro:bit上。 你也可以用你自己的文本编辑器(Sublime 3和Atom)，但是你必须把代码存储至micro:bit.这样做可能会比较麻烦一些。或者，你可以用一个[micro:bit仿真器](https://create.withcode.uk/)来测试代码。这种方法非常有效。你不需要每次下载.hex文件，它可以使修改错误的代码变得更加简单。

一旦设置成功，用一根USB线将micro:bit连接至你的电脑。USB线连接micro:bit背面的顶部接口。当准备存储代码的时候，micro:bit会亮起黄色的光。如果你用的是仿真器，你就可以忽略这一步了。如果你不是用仿真器的话，请停止阅读，按照上面说的操作即可。


## 制作蛇的六个简易步骤!
---

通过将代码分为不同的部分，游戏的每个部分都可以单独测试以确保它们能够正常运行。

1.加载代码库
2.初始化变量
3.创建主循环
4.显示蛇和食物
5.移动蛇
6.设置输赢条件

通过不断地检查代码，我们可以确保目前所写的代码都是正确的。


### 步骤 1 – 加载代码库  

因为这个项目比较简单，我们只需要默认的micro:bit代码库。这个叫做randint的函数可以生成我们所需要的随机数。 

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/2-2.png)

### 步骤 2 – 初始化变量  

待会儿，我们将用到一些变量。

Micro:bit板子上的一个点可以用一个[x,y]的坐标序列展示，x代表行， y代表列。一列点就是一条蛇（是的，一列坐标序列就组成了蛇哦！），因为它包含了一个以上的点。 它在屏幕左上角的一个单独的像素点开始，以（0,0）为坐标。之后，更多的点将会加入到这个列队中。食物则是一个单独的像素点，随机地分布在某个地方（不在同一行或同一列）。

每个方向都是由一个坐标序列组成，包含在行的方向增加或减少一点，或者是在列的方向增加或减少一点(本质上来说就是一个矢量)。例如，向右是由[1,0]表示，也就是在行的方向前进一步，在列的方向不变。蛇默认是朝右边移动，也就是方向序列中的第一选项。要让蛇朝左转弯，我们只需要进行到序列的下一个方向（朝右 -> 朝上 -> 朝左 -> 朝下 -> 朝右)。要让蛇朝右边转弯，我们需要去到序列的初始方向选项。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/3-4.png)

### 步骤 3 – 创建主循环  

循环中的代码重复运行无数次，或一直运行直到循环被破坏。记住，这是Python,因此所有后续行都需要缩进。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/4-2.png)

### Step 4 – 显示蛇和食物  

首先，我们需要清除之前绘制的所有东西以便于我们以一个空白屏幕开始。接下来，我们要绘制食物，用显示屏上的一个亮着的点来表示。之后，我们通过蛇的序列和以中等亮度绘制每个单独的像素点来进行循环。然后，下一次在屏幕上绘制之前，让程序暂停0.8秒。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/5-2.png)

运行代码
时常检查代码保证所有代码正常运行是非常重要的。在这这个时候，micro:bit板子上应该有2个像素点亮起来了。按住复位键，食物粒子将移动到另一个位置。 

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/6.gif)

### 步骤 5 – 移动  

移动蛇，看看接下来会发生什么。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/7-2.png)

所有的代码都应该放置在上一段的显示代码的顶部。第一行代码决定了蛇的下一个像素点将移动到哪里。基于当前蛇头的位置，添加方向（就行和列而言），我们可以找到下一个像素点。通过选择modulo 5,我们可以把蛇的运动限制在每个边的附近。

如果下一个点被蛇的身体占据了，会发生什么呢？在这种情况下，程序就会崩溃，游戏结束。记住这次崩溃使while：True循环停止运行。

下一个点现在成了新的蛇头。接下来，我们要检查一个食物是否被蛇吃了。如果是的话，那么应该生成一个新的食物。如果不是的话，要删掉蛇尾，让蛇只是简单地移动，而不是仅仅变长。 

运行代码
当你意识到游戏想获胜是不可能的时候，你可能会生气。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/8.gif)

### 步骤 6 – 游戏获胜  

这一段代码应该放置在显示代码的顶端和运动代码的下方。常常检查看看蛇是否已经占据了25个像素点，也就是整个屏幕。如果蛇已经占满了屏幕，玩家就获胜了。

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/9-2.png)

### 制作成功  

尽情地享受这个贪吃蛇游戏带来的乐趣吧！

![](https://www.elecfreaks.com/wp-content/uploads/2018/03/10.gif)


## 常见问题
---


## 相关阅读  
---

[Micro:bit小小发明家课程01:音乐播放器](/Micro_bit_Tinker_Kit_Case_01_Music_Machine_CN/)                        
[Micro:bit小小发明家课程02:智能灯](/Micro_bit_Tinker_Kit_Case_02_Smart_Light_CN/)   
[Micro:bit小小发明家课程03:电子琴](/Micro_bit_Tinker_Kit_Case_03_Electro_Theremin_CN/)   
[Micro:bit小小发明家课程04:报警装置](/Micro_bit_Tinker_Kit_Case_04_Simple_Alarm_Box_CN/)   
[Micro:bit小小发明家课程05:土壤湿度检测](/Micro_bit_Tinker_Kit_Case_05_Plant_Monitoring_Device_CN/)   
[Micro:bit小小发明家课程06:入侵检测](/Micro_bit_Tinker_Kit_Case_06_Intruder_Detection_CN/)   
[Micro:bit小小发明家课程07:喂鱼器](/Micro_bit_Tinker_Kit_Case_07_Fish_Feeder_CN/)  
[Micro:bit小小发明家课程08:运动检测](/Micro_bit_Tinker_Kit_Case_08_Motion_Detector_CN/)   
[Micro:bit小小发明家课程09:测谎仪](/Micro_bit_Tinker_Kit_Case_09_Lie_Detector_CN/)   
[Micro:bit小小发明家课程10:乒乓球游戏](/Micro_bit_Tinker_Kit_Case_10_PADDLEBALLSUPERSMASHEM_CN/)   
[Micro:bit小小发明家课程11:躲避小行星](/Micro_bit_Tinker_Kit_Case_11_Avoid_Asteroids_CN/)   
[Micro:bit小小发明家课程12:遥控小车](/Micro_bit_Tinker_Kit_Case_12_Remote_Control_Everything_CN/)   
[Micro:bit小小发明家课程13:micro:bit小车](/Micro_bit_Tinker_Kit_Case_13_Micro_Bit_Car_CN/)   
[Micro:bit小小发明家课程14:抛煎饼游戏](/Micro_bit_Tinker_Kit_Case_14_Flipping_Pancakes_CN/)   
[Micro:bit小小发明家课程15:跑迷宫游戏](/Micro_bit_Tinker_Kit_Case_15_Maze_Runner_CN/)   
[Micro:bit小小发明家课程16:速算游戏](/Micro_bit_Tinker_Kit_Case_16_QUICK_MATHS_CN/)  
[Micro:bit小小发明家课程17:猜音调游戏](/Micro_bit_Tinker_Kit_Case_17_Pitch_Perfect_CN/)  
[Micro:bit小小发明家课程18:手指灵敏度游戏](/Micro_bit_Tinker_Kit_Case_18_Finger_Dexterity_CN/)  
[Micro:bit小小发明家课程19:电子水平仪](/Micro_bit_Tinker_Kit_Case_19_Electric_Spirit_Level_CN/)   
[Micro:bit小小发明家课程20:太空射击游戏](/Micro_bit_Tinker_Kit_Case_20_Space_Shooter_CN/)  
[Micro:bit小小发明家课程21:飞行的小鸟游戏](/Micro_bit_Tinker_Kit_Case_21_Flappy_Bird_CN/)   
[Micro:bit小小发明家课程22:摩尔斯代码信息传输](/Micro_bit_Tinker_Kit_Case_22_Wire_Transmission_CN/)   

