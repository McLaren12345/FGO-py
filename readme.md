> 考试结束,低空飘过  
> 新年福袋想要综合排名(分先后,斜体之后有卡池):  
> 术尼禄/*伊莉雅*/*莉莉丝*/*剑尼禄*/黑骑呆/阿比/*魔总*/老福/*闪闪*/其余待定  
> 许愿伊莉雅和美游  

GitHub项目地址:[https://github.com/hgjazhgj/FGO-py/](https://github.com/hgjazhgj/FGO-py/)  
当前版本v2.8.8
快速跳转:[版本记录](#版本记录-Version-Logs)
# 警告  
**[<<哔哩哔哩游戏平台用户协议V1.0.0>>](https://yhxy.biligame.com/)第11条第2款中规定:**  
**用户不得通过不正当的手段或其他不公平的手段使用本平台游戏、本平台服务或参与本平台活动。**  
**用户不得干扰本平台正常地提供游戏和服务，包括但不限于：攻击、侵入本平台的网站服务器，或集中时间段内以超出正常用户登录需求的高频率登录或尝试登录服务器从而使网站服务器过载；破解、修改本平台提供的本平台游戏程序；攻击、侵入本平台游戏的服务器/游戏服务器端程序或使游戏服务器过载；制作、发布、传播、使用任何形式的妨碍游戏公平性的辅助工具或程序(包括但不限于“外挂”, “外挂”是指独立于游戏软件之外的，能够在游戏运行的同时影响游戏操作的所有程序，包括但不限于模拟用户操作、改变操作环境、修改数据等一切类型）。用户不得：利用程序的漏洞和错误(Bug)破坏游戏的正常进行或传播该漏洞或错误(Bug)；不合理地干扰或阻碍他人使用本平台所提供的游戏和服务；通过异常或者非法的方式使用本平台游戏(包括但不限于利用本平台游戏登录游戏私服)；使用异常的方法登录游戏（包括但不限于使用非本平台开发、授权或认可的第三方软件、系统登录游戏）、使用网络加速器等外挂软件或机器人程序等恶意破坏服务设施、扰乱正常服务秩序的行为；修改、翻译、注释、整理、汇编、演绎本平台游戏；利用本平台游戏或者线上游戏系统可能存在的技术缺陷或漏洞而以各种形式为自己及他人牟利（包括但不限于复制游戏虚拟物品等）或者从事其他不正当行为等。**  
**由于使用本脚本而导致的包括但不限于上述各项的损失本人概不负责,您下载并使用该脚本即代表您已知晓使用脚本可能带来的风险并愿意承担可能出现的后果,望周知**  
<del>但是fgo内部的用户条款好像没有限制脚本的使用</del>  
***  
# 使用说明 Instruction  
本readme仅使用了基本markdown语法,你可以在任意编辑器上查看  
本readme仅仅教你怎么用这个脚本来玩fgo,并不会告诉你代码是怎么写的,代码里也没有一行说明性质的注释,所以有几行代码我自己都得看一会儿才看得懂  
模拟器必须全屏显示在1920\*1080的显示屏上,窗口可以被遮挡但是不能被隐藏或最小化  
若要用于真机,参见[这里](#如何将此脚本应用于真机)  
虽然改几行代码就能应用于任意分辨率,但这可能导致识别问题,需要手动修改精度限制  
你的电脑上要有adb([官方文档](https://developer.android.google.cn/studio/command-line/adb),[官方下载](https://adbshell.com/upload/adb.zip))要下载的话直接点这里的下载链接,百度上搜adb都出来的都是些什么乱七八糟的...  
你得会一点点python3,不用很多  
使用了以下库:  
`time` `os` `numpy` `cv2` `win32con` `win32ui` `win32gui`  
没有的直接`pip install`  

**主程序是fgo_py.py**,直接运行或编辑  
代码最后几行就是主程序示例,  
建议在命令行交互中调用函数以执行脚本,以免初始化时反复加载资源  
你也可以把它作为一个模块导入后调用里面的函数  

+ 在点击列表中第一个关卡就能进入选择助战界面的界面启动`main`函数来清空体力条,该函数有至少三个参数:要吃的苹果数(默认0),苹果种类(0金1银2铜3彩,默认0),战斗函数(默认`oneBattle`).之后是要向战斗函数中传递的各项参数  
+ 在进入战斗后尚未选卡的界面启动`oneBattle`函数来完成这一战斗,若传入一个有三个`int`的`list`就会在各stage优先攻击左起自1开始编号的敌人  
+ 在进入战斗后尚未选卡的界面启动`otk`函数来完成自定义的三回合速刷,需手动配置操作行为

这个脚本是会自动放技能(可以设定,默认不用技能),自动放宝具(可以设定,默认充能满就直接放宝具),自动选卡(优先三色chain,否则优先红卡).合理设定后实战7-12回合能够刷完无限池终本  
每一回合的战斗都会输出相应信息用于debug,包括:  

1. 当前回合数  
2. 当前stage数  
3. 这一stage已经进行的回合数  
4. 各技能是否冷却完毕  
5. 各宝具是否充能完毕  
6. 各指令卡颜色  
7. 选择的指令卡序列  

我的联系方式  
qq 979449732  
email huguangjing0411@geektip.cc  
有任何问题或bug反馈请联系,觉得有帮助请为我star  
请向可怜的非酋投喂<del>圣晶石</del>彩苹果  
## 你需要修改slnPath,adbPath和wndTitle  
`slnPath`是本解决方案的绝对位置,方便你把代码和其他资源分开放  
`adbpath`要根据你的设备连接方式进行修改(在fgo_shell.py文件中)  
`wndTitle`为显示游戏画面的窗口标题,该窗口大小必须为1920\*1080且没有边框  
如果你的屏幕不是1920\*1080的,你就得把游戏的显示画面调整到正好1920\*1080并且在每一次截图后把边框裁掉  
## 你可以修改skillInfo数组
`skillInfo`列表记录了技能的信息  
`skillInfo[编队中的第i个从者][的第j个技能]=[该技能的最小使用stage数,在该stage的最小使用回合数,指向的目标(没有目标置0)]`  
也就是说,若不使用技能就`skillInfo[i][j][0]=4`  
这样的安排足以应付日常周回的各种情况,比如三面Boss充能五格,就把保命技能=[3,6,0]  
## 你可以修改houguInfo数组
`houguInfo`列表记录了宝具的信息  
`houguInfo[编队中的第i个从者]=[的宝具的最小使用stage数,在该stage的最小使用回合数,是否优先使用(优先置1)]`  
## 助战 Friends
由于当前版本可以筛选礼装,本脚本又不需要限定特定从者,所以此功能默认是禁用的,你可以在`main`函数中`chooseFriend`的注释挪到他的下一行来启用助战选取功能  
你需要事先将你期望的各种助战的样子截图为png放在asserts/friend下,参照asserts/friend/unused中的文件  
**被截图范围都应该可以点击来选中该好友**,实际的点击位置为图片的正中央  
如果你用的是模拟器,请使用本程序的`screenShot`函数来截图而不要用模拟器自带的截图,更不要用<kbd>prtSc</kbd>键或其他工具来截图,这可能会导致识别错误  
如果你用的是手机,`screenShot`函数也可以大大方便你的操作  
`screenShot`函数已不在主程序中使用,你需要手动解除注释  
使用`screenShot`函数时,请在手机的/sdcard目录下新建一个名为adbtemp的文件夹  
助战截图的名称中若有下划线'_',且下划线之前的部分为km,ml,cba,则代表好友就挂的是孔明,梅林,十八岁美少女,这会影响助战技能的使用,参见`chooseFriend`函数具体实现  
## 如何将此脚本应用于真机
v2.7.x及之前版本能在任意支持python和adb的系统上用于任何Android设备,v2.7版本的代码现在也是可以用的尽管可能不是那么稳定,x2.8.0及之后的版本仅仅由于截图方式由adb改为win32api而只能在windows系统上用于1920*1080的屏幕,如果使用真机,要么把手机屏幕找一个投屏软件投到屏幕上要么把`Check.__init__()`中的注释挪到最后两行以启用先前版本的截图函数,注意,由于当前版本是基于新截图方式进行的优化,进行此替换虽然不会导致错误,但是会使运行效率比v2.7.x还要低得多得多  
使用真机时,你还需要以下操作:  
如果不是16:9屏幕,你得修改`dpx`为左侧的蓝边宽度(4:3屏幕上方有蓝边?...自己改代码去吧),例如2160\*1080就`dpx=(2160-1920)/2=120`  
理论上来说,你只需要把fgo_shell.py文件替换成适合你的设备的同名文件就可以了,但是通常真机会比较卡,你可能需要在各种地方添加延迟,并适当增加`Fuse.__max`  
你还可能需要适当增加各处识别的`delta`值,0为完全匹配,1为完全不匹配(`TM_SQDIFF_NORMED`)
# 注意 Caution
模拟器窗口必须保持全屏显示,不可最小化,所以强烈建议关闭模拟器的"老板键(boss key)"功能  
若战斗失败会自动撤退并留下记录然后继续下一把(若战斗失败就发出噪音把你吵醒起来改代码?倒也不是不能做到啦~)  
有些时候对从者头像的识别会有错误,*虽然在不断以各种方式优化,但这个问题至今未完全解决* ,所以**如果你打算睡觉去,就不要用后排的技能**,否则万一一觉起来发现打第二把的时候就卡住了...  
# Q&A&杂谈  
2018年9月,一件大事发生了,没有人知道这个游戏正在经历一场变革  
那时我刚上大学,年轻人有的是时间,有的是精力,就开始研究怎么压榨电脑的剩余价值.答案就是这个脚本的前身,**[FGO-C](https://www.bilibili.com/video/av34399081)**,代码已经被删掉了,但是当时录了个视频.那时候我的脚本功能跟现在GitHub上别人写的脚本差不多简陋,就是想尽一切办法三回合宝具速刷,速刷不了就凉凉.但是那时候尼禄祭终本是术阶的,计算器一敲正好可以小莫稳定3t,当时NGA上还有专门的np回收计算程序,C#写的,[帖子](https://bbs.nga.cn/read.php?tid=15337515&_fp=16),[GitHub项目](https://github.com/markpanyi/PerpetualNPPerformance)**没错我挖了一晚上的坟把这个帖子找到了!** VisualStudio上装了.NET桌面开发的可以直接打开,但是这个程序有bug,你得在编译后把CraftEInfo.xml和SkillInfo.xml放到编译结果所在目录的Data文件夹里才能正常运行.54年10月31日,尼禄·克劳狄乌斯继承皇位,成为当时罗马帝国即位年龄最小的皇帝.2018年10月31日,我和千千万万玩家一起肝尼禄祭.那次的尼禄祭,283池.  
尝到了这么大的甜头,怎么能停得下来!当时没有现在这么高级的功能,只有用Win32API的keybd_event来模拟键盘事件,必须保持模拟器窗口完整显示并处于激活状态.当初为什么不用adb呢?因为**adb算是对Android的操作,有可能被检测**,这也是为什么日服禁root禁USB调试禁模拟器的原因,而**用Windows的函数隔着一层虚拟机你拿头来检测我** !这样的日子过得挺安逸,直到有一天,我突然发现我当时用的mumu模拟器禁用了虚拟键盘事件,可能是处于效率和延时考虑换成了更底层的实现,这要我来写的话就得创建虚拟设备然后发送硬件扫描码了.有点头大.于是我下定决心换用adb.同时也把语言改成了python,纯粹是因为python处理字符串简单.  
众所周知,python是万能的.于是我不断开发这个脚本,尝试了各种各样的功能,那些曾经使用现已废弃的部分仍可见于被注释掉的部分.先是PIL.Image读取像素进行识别,然后进化成了open-cv的matchTemplate.终于,从"开环控制"变为了"闭环控制".也就是你现在看到的这个脚本.下一步,也就是v3.0版本的目标,一是建立所有从者的数据库,标明技能宝具的详细信息,二是在战斗中获取敌方的信息和更多己方的信息,三是依靠一二两条中的信息在战斗中实现真正智能化的技能施放和选卡.也就是**我能打过的高难用同样的阵容脚本也能打个八九不离十**.而至于本脚本的究极形态,就是**服务器维护我也维护,维护结束我立刻上号挂机,把玩家变成只会抽卡的机器** .当然我有生之年要是没有利益可图就应该不会开发v3.0版,倒不如说2.8这一版本已经基本解决了玩家肝度和游戏强度之间的矛盾,算是接近我心中的理想形态了.讲真有哪些时间去写超级复杂但提升不大的代码不如老老实实把那些时间用在亲自打游戏上.  
自古以来,我就有在模拟器上把每个技能每张指令卡都设置一个键位然后用键盘玩fgo的习惯,当初正是因为敲键盘只有按下弹起两种消息,不想鼠标要设定坐标,相对简单明了.比如看到'A'就知道时使用第一个技能,看到(109,860)就一脸懵B,尽管它们都代表使用第一个从者的第一个技能.这一思想贯彻到了现在,代码里的key就是干的这件事.这样虽然看起来很蠢,一点都不"面向对象"(虽然我没对象,在线征婚啊喂!<del><<在GitHub上寻求邂逅是否搞错了什么>></del>),但却是**别人的代码得好几个文件加起来上千行,我的代码只要两个文件300+行,还功能比别人强,debug比别人容易**的根本原因.<del>我就是喜欢把所有代码挤在一个文件里怎么了!</del>别人只能三回合(我因此把那些代码叫做"三回合代码"),而像我一样能**实现智能战斗不间断,不靠礼装不用拐** 的,github上怕不是**只有我一个**.  
承接上文,我自知这个脚本功能过于强大,强大到了严重影响游戏平衡,改变游戏性质,急剧扩大玩家间差异的程度.就算是在GitHub上开源我都是下了决心的.2020年刚过,B站up主[MCLAREN--](https://space.bilibili.com/13033022)搞了一套硬件来在iOS上跑脚本,虽然他的代码就是"三回合代码",硬件也非常简单,但他似乎是第一个做出来的,反正人家就是比我勤快([视频](https://www.bilibili.com/video/av82095192),[专栏](https://www.bilibili.com/read/cv4303413)).注意到**硬件不被B站的条款限制** (虽然法律还是会管的),所以等我什么时候有空了,就搞一套差不多的硬件,只要把我的脚本底层交互接口从adb到伺服电机这么一改,然后新瓶装旧酒,挂羊头卖狗肉地出个视频既可以让网友们看到我的脚本,又不怕帐号被封,岂不美哉!  
GitHub上从来不缺有思想有执行力的程序员,希望这个脚本能越写越好,祈祷这个世界再无BUG.  
另:难道iOS就不能软件调试吗?,好像[appium](https://github.com/appium/appium)是可以做到的,甚至能3Dtouch,用起来也方便.因为我用的是Android,所以对此并不了解,但我坚持**能用软件解决就不用硬件**的原则.希望有大神能扩展一下我的代码,反正就是改几个底层函数,让iOS也能用.
# 版本记录 Version Logs  
## 2020/01/13 v2.9.0  
代码重构,无实质性变化  
把所有(依赖于adb的)底层交互接口放到了一个新文件里,如果要换平台应用脚本,只要更改新文件里面的内容就行了  
看了一波下来突然发现我的脚本封装地是真滴好,只有三个函数跟少数变量是跟fgo运行所在平台相关的,他们是:  
`tap`,`swipe`,`screenShot`  
并且对于当前版本的脚本,你几乎用不到`chooseFrined`函数,截图识别也跟adb无关,也就是说,你甚至可以不写`swipe`和`screenShot`函数,因为在所有其他地方都没有使用这两个函数,就是不停地点点点  
我要不要再把所有依赖Windows的函数也搞个文件放着呢?应该没有人吃了空用Linux打fgo把...<del>mac?那是什么我不知道</del>
## 2020/01/12 v2.8.8  
bug修复:现在在战斗结束时如果提示加好友会更稳定地拒绝  
说明:此前版本中由于点击时机不精确有可能导致卡在加好友界面  
## 2020/01/12 v2.8.7  
重大bug修复:现在每截一次图就会释放在调用win32api时分配的内存  
说明:在此前的版本中进行大约9场battle就会占用大约8G内存进而导致截图中的某一步分配内存失败,  因此所有使用v2.8.x版本的用户都应该立刻安装此更新  
果然,珍爱生命,远离win32api  
## 2020/01/11 v2.8.6
优化:现在在好友选择界面发现没有好友时(多半是由于使用了过于严苛的筛选条件导致的),会刷新一次好友列表,再发现列表为空才会GG  
优化:`chooseFriend`函数现在不会无止境地找好友,最多识别`Fuse.__max`(默认300)个页面
## 2020/01/10  
在readme中加入了adb的下载链接,百度上搜adb都出来的都是些什么乱七八糟的...  
## 2020/01/09 v2.8.5  
延时调整  
## 2020/01/09 v2.8.4  
bug修复:现在不会试图使用被封印的宝具  
对于这个bug的修复可能有bug  
## 2020/01/09 v2.8.3  
期末考结束了...  
稳定性大优化  
全面修订readme  
## 2020/01/08 v2.8.2  
截图从<某个已经消失的版本>的qt改回win32api了...  
修改了一些判定的模板图片  
由于截图效率的提高,正在尝试用多帧来进行一次判定来提高可靠性,比如houguinfo  
## 2020/01/08 v2.8.0  
稳定性优化  
肝!
## 2020/01/07 v2.8.0beta  
紧急更新  
本次更新内容可靠性未经充分验证,请谨慎下载使用  
使用了win32api代替之前的adb进行截图,单次截图时间从1s级别减低到了10ms级别  
这段代码是不带裁剪和缩放的,所以**需要模拟器在正好1920\*1080的显示器上全屏显示,真机的话要用投屏软件**  
由于之前的代码有一些地方是依赖截图的耗时来进行延迟的,这一延迟消失后可能引发各种各样的问题,所以我正在一点一点地在必要的地方加上显式延迟,但是仍然会有疏漏,之后发现一个解决一个,慢慢改  
## 2020/01/03 v2.7.0  
打版本日志的时候突然发现已经2020年了...期末考好累...  
圣诞活动7号晚上开始,但是期末考9号才结束...  
所以复习放一边去,先把脚本给写了  
重大bug修复,带指向的技能现在会正确地施放了(尽管识别错误的问题仍然存在)  
微调了部分按键坐标,**现在你可以吃银苹果和铜苹果了**  
小优化,切换目标后加了冗余点击以关闭在点击已选中目标时产生的敌人详情对话框  
增加了所谓"快速换装(setSkillInfo)"函数,**先把配置写好,然后活动一开就上号挂机岂不美哉**!  
flag:我圣诞要吃光苹果,当前金苹果当量287  
## 2019/11/26 v2.6.0
蓝叠模拟器更到最新版就不会闪退了  
chooseFriend函数还是挺重要的,要用来选取特定从者  
明天(2019年11月27日星期三)上午8:30通关主线第8话(前篇)后开启炎舞击退战,
增加了一小段代码用于otk,现在直接运行脚本就是单次执行该脚本  
这段代码专用于"三美少女队",如果你没有bba/cba中的任何一个,或嫖不到cba,告辞.  
需要极地迦勒底制服  
**本次活动特攻是"特殊的魔放",会稀释其他的倍率,可恶!**  
## 2019/11/10 v2.5.2
版本更新后蓝叠模拟器闪退,在物理机上的兼容性未发现显著问题.  
版本更新后可以对助战礼装进行筛选,chooseFriend函数变得不再重要,已在主程序中禁用.  
