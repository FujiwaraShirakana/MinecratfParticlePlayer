# MinecratfParticlePlayer
# **我的世界粒子特效Midi播放器（以下简称MPMP）** <br><br>

## 介绍
---
### &emsp;项目名：我的世界粒子特效Midi播放器（粒子特效指令音乐）<br>
### &emsp;作者：训练有素的藤原白叶（藤原白葉）

### &emsp;测试视频地址：  [ **演示1** ](https://www.bilibili.com/video/BV11y4y1L7jT)      [ **演示2** ](https://www.bilibili.com/video/BV1uT4y1P7CX)

### &emsp;软件架构：
&emsp;&emsp;&emsp;&emsp;**1.**  仅包含.h头文件<br>
&emsp;&emsp;&emsp;&emsp;**2.**  需要自己创建C++（Cpp）文件并使用主函数调用头文件中函数<br>
&emsp;&emsp;&emsp;&emsp;**3.**  不存在.exe可执行文件（未来可能会加入）<br>

### &emsp;关于
&emsp;&emsp;&emsp;&emsp;MPMP是一个用于制作Minecraft原版指令特效粒子的工具。<br>
&emsp;&emsp;&emsp;&emsp;它可以通过MIDI的数据，自动确定坐标并生成一串mcfunction<br>
&emsp;&emsp;&emsp;&emsp;以在MC中显示粒子特效连线。<br>
&emsp;&emsp;&emsp;&emsp;MPMP可以简化制作MC特效音乐，省略制作过程中的重复步骤。<br> <br>

## 快速开始
---
### &emsp;安装：
#### &emsp;&emsp;1.  安装C++：
&emsp;&emsp;&emsp;&emsp; **i)：**   安装相关IDE，如&emsp;&emsp;&emsp;[DEVCPP(外部下载站，请注意计算机安全)](https://sourceforge.net/projects/orwelldevcpp/) &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[VisualStudio(官网下载)](https://visualstudio.microsoft.com/zh-hans/)
#### &emsp;&emsp;2.  安装该项目：
&emsp;&emsp;&emsp;&emsp; **i）：** 点击本页面克隆/下载按钮，并点击下载ZIP<br>
&emsp;&emsp;&emsp;&emsp; **ii）：** 下载发行版中MC粒子特效Midi播放器并解压<br>
#### &emsp;&emsp;3.  配置MC环境：
&emsp;&emsp;&emsp;&emsp; **i) ：** 安装Minecraft - 1.16.5（Fabric）<br>
&emsp;&emsp;&emsp;&emsp; **ii) ：** 下载ColorBlock（1.16.5-Fabric）[点我下载](https://www.mcbbs.net/thread-917845-1-1.html)<br>
&emsp;&emsp;&emsp;&emsp; **iii) ：** 按照说明中的提示调用函数<br>

### &emsp;一些必须了解的基础知识：
#### &emsp;&emsp;1.  MC程序基础：
&emsp;&emsp;&emsp;&emsp; **i）：** `MC刻(tick)` MC游戏的时间单位为tick，它与现实中秒的对应关系为20:1，<br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;即mc是以20的tps（tick per second）运行<br>
&emsp;&emsp;&emsp;&emsp; **ii）：** `MCFUNCTION` MC高版本提供的一个新功能，可以简单的理解为多个指令的<br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;集合，它可以实现用一条指令执行多条指令<br>
&emsp;&emsp;&emsp;&emsp; **iii）：** `MCDATAPACK` MC高版本新功能，数据包，可以对原版内容进行修改，可以<br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;定义自己的Mcfunction<br>
#### &emsp;&emsp;2.  需要用到的MC指令：
&emsp;&emsp;&emsp;&emsp; **i）：**[execute](https://minecraft.fandom.com/zh/wiki/%E5%91%BD%E4%BB%A4/execute)<br>
&emsp;&emsp;&emsp;&emsp; **ii）：**[scorebroad](https://minecraft.fandom.com/zh/wiki/%E5%91%BD%E4%BB%A4/scoreboard)<br>
&emsp;&emsp;&emsp;&emsp; **iii）：**[particle](https://minecraft.fandom.com/zh/wiki/%E5%91%BD%E4%BB%A4/particle)<br>

### &emsp;使用说明1（纯特效线条函数，即particle.h）：
&emsp;&emsp;&emsp;&emsp; **1.**   按照以上方法安装完毕后，进入Minecraft - 1.16.5，新建一个地图，<br>&emsp;&emsp;&emsp;&emsp;并创建一个名为Timer的计分板<br>
&emsp;&emsp;&emsp;&emsp; **2.**   将项目中的datapack文件夹复制入新建世界的存档文件中<br>
&emsp;&emsp;&emsp;&emsp; **3.**   在项目中创建一个源文件（.cpp）引用Particle.h 在其下创建一个主函<br>&emsp;&emsp;&emsp;&emsp;数（main）<br>
&emsp;&emsp;&emsp;&emsp; **4.**   在main函数头部写入文件打开函数，打开文件指针file1。<br>
&emsp;&emsp;&emsp;&emsp; **5.**   调用实参为（起点X，终点X，起点Y，终点Y，起点Z，终点Z，测试数值<br>&emsp;&emsp;&emsp;&emsp;（填10是最完美的），文件名（在本版本中无作用，是迁移高版本后遗留<br>&emsp;&emsp;&emsp;&emsp;的参数））<br>

### &emsp;使用说明2（带向导的自动化生成，即MCPARTICLEMIDI.....h）：
&emsp;&emsp;&emsp;&emsp; **1.**   按照以上方法安装完毕后，进入Minecraft - 1.16.5，新建一个地图，并<br>&emsp;&emsp;&emsp;&emsp;创建一个名为Timer的计分板。<br>
&emsp;&emsp;&emsp;&emsp; **2.**   将项目中的datapack文件夹复制入新建世界的存档文件中。<br>
&emsp;&emsp;&emsp;&emsp; **3.**   复制项目至一个文件夹，并在项目中创建一个源文件（.cpp）引用MCPARTI<br>&emsp;&emsp;&emsp;&emsp;CLEMIDIPLAYERMAINCONTROL.h 在其下创建一个主函数（main）。<br>
&emsp;&emsp;&emsp;&emsp; **4.**   在main函数头部调用函数StartProject（普通线条）或者StartRound（连<br>&emsp;&emsp;&emsp;&emsp;续相切圆），第一次调用会在根目录创建一个名为input.txt的文件。<br>
&emsp;&emsp;&emsp;&emsp; **5.**   打开input.txt，使用工具提取Midi的音符（建议使用Audio2Minecraft）<br>&emsp;&emsp;&emsp;&emsp;将其中的起始时间一列与Midi音高一列复制入该文件（每一行为 起始时间 Midi<br>&emsp;&emsp;&emsp;&emsp;音高，如下图），需要将其中制表符替换为空格。<br>
![如图](Imageimage.png)
&emsp;&emsp;&emsp;&emsp; **6.**   再次运行函数，会在根目录生成一个Temp.mcfunction的文件，重命名之，将<br>&emsp;&emsp;&emsp;&emsp;其中Temp改为纯小写字母组成的字符串。<br>
&emsp;&emsp;&emsp;&emsp; **7.**   放入datapack的function文件夹内，进入存档，使用循环命令方块调用<br>&emsp;&emsp;&emsp;&emsp;（不包含播放声音的函数，是因为大家用的音源资源包都不一样，如果需要<br>&emsp;&emsp;&emsp;&emsp;以后会加上）<br>


> 1月28日更新：加入了新的两个函数（playsound_setblock和EndParticle）前者是自动playsound和setblock，后者是末点特效，运行这两个函数均会在根目录下创建一个Input_SB.txt，这个文件与input.txt的区别是在input.txt的基础上加入了一列力度（音量）。可以通过修改EndParticle中For循环中函数来实现切换末点特效。


## 将要做的
---
### &emsp;更多粒子特效：
#### &emsp;&emsp;基础线条：
&emsp;&emsp;&emsp;&emsp;<del>直线（普通直线和伪倒影效果直线）</del><br>
&emsp;&emsp;&emsp;&emsp;<del>抛物线（普通抛物线和伪倒影效果抛物线与结束点圈阵的抛物线）</del><br>
&emsp;&emsp;&emsp;&emsp;<del>正弦/余弦曲线。</del><br>
&emsp;&emsp;&emsp;&emsp;<del>螺线与螺线组。</del><br>
&emsp;&emsp;&emsp;&emsp;<del>平面连续相切圆和带有Y轴的连续相切圆</del><br>
&emsp;&emsp;&emsp;&emsp;<del>笛卡尔叶形线</del><br>
&emsp;&emsp;&emsp;&emsp;<del>星型线</del><br>
&emsp;&emsp;&emsp;&emsp;<del>倒映形线条</del><br>
&emsp;&emsp;&emsp;&emsp;<del>线条消失前散开</del><br>
&emsp;&emsp;&emsp;&emsp;贝塞尔曲线<br>
&emsp;&emsp;&emsp;&emsp;傅里叶变换<br>
&emsp;&emsp;&emsp;&emsp;钱学森弹道轨迹<br>
&emsp;&emsp;&emsp;&emsp;随机轨迹曲线<br>
&emsp;&emsp;&emsp;&emsp;<del>七影蝶飞行</del><br>
&emsp;&emsp;&emsp;&emsp;心形“抛物线”<br>
&emsp;&emsp;&emsp;&emsp;导弹作为线条头部<br>
#### &emsp;&emsp;音符特效：
&emsp;&emsp;&emsp;&emsp;<del>扩大的圆圈</del><br>
&emsp;&emsp;&emsp;&emsp;<del>螺旋线</del><br>
&emsp;&emsp;&emsp;&emsp;<del>星星</del><br>
&emsp;&emsp;&emsp;&emsp;<del>心形线</del><br>
&emsp;&emsp;&emsp;&emsp;<del>蝴蝶（翅膀会飞，会动的）</del><br>
&emsp;&emsp;&emsp;&emsp;米国和霓虹的城市名<br>
&emsp;&emsp;&emsp;&emsp;爆炸特效<br>
&emsp;&emsp;&emsp;&emsp;各种花里胡哨的特效<br>

### &emsp;MIDI：
&emsp;&emsp;&emsp;&emsp;MIDI文件读取<br>
&emsp;&emsp;&emsp;&emsp;MIDI文件编辑<br>
&emsp;&emsp;&emsp;&emsp;MIDI文件导出<br>
### &emsp;Playsound：
&emsp;&emsp;&emsp;&emsp;<del>自动处理播放声音指令</del><br>
&emsp;&emsp;&emsp;&emsp;适配各个网络上存在的音源资源包<br>
### &emsp;setblock：
&emsp;&emsp;&emsp;&emsp;<del>在每一个音符处放置方块</del><br>
### &emsp;可视化界面：
&emsp;&emsp;&emsp;&emsp;.exe可执行程序，可视化界面操作<br>
### &emsp;基岩版适配：
&emsp;&emsp;&emsp;&emsp;基岩版适配<br>
## 作者的话
---

本人目前在搞MC计算机，以及一些其他有趣的项目，所以以后可能会退坑MC音乐，Midi也不会怎么做了（最早是因为对Summer Pockets的女主鳴瀬しろは的爱才去做这些midi音乐），以后可能在这些地方不会再活跃。作者本人是一个物理系的大学生，但有着对音乐，美术以及编程的浓厚兴趣，而开发此项目最早只是为了帮助我处理一些视频制作中的重复性步骤，刚一开始写的代码非常垃圾，经过几次重构之后，大多数的bug都得到了修复，代码也变得勉强能看了（）。如今将这个项目开源，是希望以后能有更多人能够创作更多优秀的作品。

这个项目开始于2018年（我刚入学高中的时候），最早的时候只是想在同学面前装个X，或者是自己做一些中看不中用的特效出来套到mc的武器上或者是套到音符盒红石音乐上，当时觉得这样非常炫酷，但是没有想法做成视频。然后到了20年的时候，我无意间看到了soma大佬的视频，然后也有了在b站发布相关视频的想法，于是就把这个项目从垃圾堆里捡了回来（），最早的时候是用mc的隐形实体标记粒子路径，然后进化到计算函数后使用多个mcfunction穷举坐标，最终进化到了如今的借助colorblockmod直接使用函数。

本人做出来的效果不如其他Up，主要还是因为没有使用材质包以及光影包，配合replaymod进行后期渲染。所以在使用的过程中加装光影和材质包效果更佳。

前段时间一直有人在b站私信我，向我询问粒子特效的制作方法，这也是我开源这个项目的理由之一，其实这个项目非常简单，只要是会写一点程序的人都可以写出来，然后就是mc的指令，mc的指令对于大多数人来说可能无从考证（wiki资料不全，没有列出指令的全部用法和全部可实现的功能）这就导致了许多人不会用指令，或者是不会使用指令深层的一些东西，而mc要实现一些有趣的东西，必须用到进阶的指令（比方说b站某Up开发的mc塔防数据包，数据包不是mod，是用纯原版指令以及物品实现功能的玩意）这个对制作者对mc指令的了解有着很高的要求，然后就是高数线代，要做粒子特效，有许多东西是需要高数线代实现的。

开源这个项目是为了简化制作粒子特效音乐的过程，而不是让某些人去批量生成此类视频赶热度蹭流量，也许有人会说：“你不也是用程序生成的吗？”要知道为了做这个项目，我将mc的指令通通学了一遍，在初中学完了线性代数以及复杂曲线方程，学习了cpp编程，在计算函数并将其程序化的过程中也废了一番苦心，最最重要的是，我一般只有开发出新的粒子效果后才会发送新的视频，不存在量产。总之就是希望大家不要借着开源程序将这个圈子变得低创化。也许还会有些人，拿该项目生成的东西盈利，这种人只能提醒他注意身体了。当然这是个开源项目，想怎么用就怎么用，就是不希望有人这样用而已。

如果对MC，P社，GalGame感兴趣，或者是对MC指令，本项目的细节有什么问题，可以联系QQ：1751842477，关注B站UID：108592413，或者加群：1105658265

## 写在后面
---

恼


