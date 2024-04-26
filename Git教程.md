# Git教程

## Git简介

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

Git有什么特点？简单来说就是：高端大气上档次！

那什么是版本控制系统？

如果你用Microsoft Word写过长篇大论，那你一定有这样的经历：

想删除一个段落，又怕将来想恢复找不回来怎么办？有办法，先把当前文件“另存为……”一个新的Word文件，再接着改，改到一定程度，再“另存为……”一个新文件，这样一直改下去，最后你的Word文档变成了这样：

![lots-of-docs](C:\Users\15278\Desktop\typora\img\0.jpeg)

过了一周，你想找回被删除的文字，但是已经记不清删除前保存在哪个文件里了，只好一个一个文件去找，真麻烦。

看着一堆乱七八糟的文件，想保留最新的一个，然后把其他的删掉，又怕哪天会用上，还不敢删，真郁闷。

更要命的是，有些部分需要你的财务同事帮助填写，于是你把文件Copy到U盘里给她（也可能通过Email发送一份给她），然后，你继续修改Word文件。一天后，同事再把Word文件传给你，此时，你必须想想，发给她之后到你收到她的文件期间，你作了哪些改动，得把你的改动和她的部分合并，真困难。

于是你想，如果有一个软件，不但能自动帮我记录每次文件的改动，还可以让同事协作编辑，这样就不用自己管理一堆类似的文件了，也不需要把文件传来传去。如果想查看某次改动，只需要在软件里瞄一眼就可以，岂不是很方便？

<iframe id="aswift_6" name="aswift_6" style="left: 0px; top: 0px; border: 0px; width: 1200px; height: 0px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="1200" height="0" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-6727358730461554&amp;output=html&amp;h=280&amp;adk=1228093153&amp;adf=982595112&amp;w=1200&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1712827051&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=2183257665&amp;ad_type=text_image&amp;format=1200x280&amp;url=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896067008724000&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=1359&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;dt=1712827051934&amp;bpp=1&amp;bdt=1188&amp;idt=1&amp;shv=r20240409&amp;mjsv=m202404100101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D4e25a865b7c1ce49%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_MaEwsqVyulF9qENFFAArAWODQbtkQ&amp;gpic=UID%3D00000d2a92790e89%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_Makoj48xzmVXn03EqSuFWduGWS9OQ&amp;eo_id_str=ID%3D080f3d570f8fc833%3AT%3D1709777629%3ART%3D1712826913%3AS%3DAA-AfjY6uexMMmwPvP2Wacgm3DiX&amp;prev_fmts=300x600%2C300x600%2C336x280%2C336x280%2C336x280%2C0x0&amp;nras=2&amp;correlator=2921071141034&amp;frm=20&amp;pv=1&amp;ga_vid=1526805260.1712827051&amp;ga_sid=1712827051&amp;ga_hid=351785732&amp;ga_fc=0&amp;u_tz=480&amp;u_his=10&amp;u_h=1080&amp;u_w=1920&amp;u_ah=1032&amp;u_aw=1920&amp;u_cd=24&amp;u_sd=1&amp;adx=526&amp;ady=930&amp;biw=1920&amp;bih=919&amp;scr_x=0&amp;scr_y=0&amp;eid=44759876%2C44759927%2C44759837%2C95328448%2C95326317%2C95329439%2C95329832%2C31082672%2C95321963%2C31082144&amp;oid=2&amp;pvsid=3520359675914449&amp;tmod=1730355895&amp;uas=0&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600&amp;fc=384&amp;brdim=-8%2C-8%2C-8%2C-8%2C1920%2C0%2C1936%2C1048%2C1920%2C919&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1.01&amp;ifi=7&amp;uci=a!7&amp;btvi=6&amp;fsb=1&amp;dtd=5" data-google-container-id="a!7" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="CMGFg4DquYUDFb1LwgUdY_gI3g" data-load-complete="true"></iframe>

这个软件用起来就应该像这个样子，能记录每次文件的改动：

| 版本 | 文件名      | 用户 | 说明                   | 日期       |
| ---- | ----------- | ---- | ---------------------- | ---------- |
| 1    | service.doc | 张三 | 删除了软件服务条款5    | 7/12 10:38 |
| 2    | service.doc | 张三 | 增加了License人数限制  | 7/12 18:09 |
| 3    | service.doc | 李四 | 财务部门调整了合同金额 | 7/13 9:51  |
| 4    | service.doc | 张三 | 延长了免费升级周期     | 7/14 15:17 |

这样，你就结束了手动管理多个“版本”的史前时代，进入到版本控制的20世纪。

### Git的诞生

很多人都知道，Linus在1991年创建了开源的Linux，从此，Linux系统不断发展，已经成为最大的服务器系统软件了。

Linus虽然创建了Linux，但Linux的壮大是靠全世界热心的志愿者参与的，这么多人在世界各地为Linux编写代码，那Linux的代码是如何管理的呢？

事实是，在2002年以前，世界各地的志愿者把源代码文件通过diff的方式发给Linus，然后由Linus本人通过手工方式合并代码！

你也许会想，为什么Linus不把Linux代码放到版本控制系统里呢？不是有CVS、SVN这些免费的版本控制系统吗？因为Linus坚定地反对CVS和SVN，这些集中式的版本控制系统不但速度慢，而且必须联网才能使用。有一些商用的版本控制系统，虽然比CVS、SVN好用，但那是付费的，和Linux的开源精神不符。

不过，到了2002年，Linux系统已经发展了十年了，代码库之大让Linus很难继续通过手工方式管理了，社区的弟兄们也对这种方式表达了强烈不满，于是Linus选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。

安定团结的大好局面在2005年就被打破了，原因是Linux社区牛人聚集，不免沾染了一些梁山好汉的江湖习气。开发Samba的Andrew试图破解BitKeeper的协议（这么干的其实也不只他一个），被BitMover公司发现了（监控工作做得不错！），于是BitMover公司怒了，要收回Linux社区的免费使用权。

Linus可以向BitMover公司道个歉，保证以后严格管教弟兄们，嗯，这是不可能的。实际情况是这样的：

Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！一个月之内，Linux系统的源码已经由Git管理了！牛是怎么定义的呢？大家可以体会一下。

Git迅速成为最流行的分布式版本控制系统，尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。

历史就是这么偶然，如果不是当年BitMover公司威胁Linux社区，可能现在我们就没有免费而超级好用的Git了。

### 集中式vs分布式

Linus一直痛恨的CVS及SVN都是集中式的版本控制系统，而Git是分布式版本控制系统，集中式和分布式版本控制系统有什么区别呢？

先说集中式版本控制系统，版本库是集中存放在中央服务器的，而干活的时候，用的都是自己的电脑，所以要先从中央服务器取得最新的版本，然后开始干活，干完活了，再把自己的活推送给中央服务器。中央服务器就好比是一个图书馆，你要改一本书，必须先从图书馆借出来，然后回到家自己改，改完了，再放回图书馆。

![central-repo](C:\Users\15278\Desktop\typora\img\l.jpeg)

集中式版本控制系统最大的毛病就是必须联网才能工作，如果在局域网内还好，带宽够大，速度够快，可如果在互联网上，遇到网速慢的话，可能提交一个10M的文件就需要5分钟，这还不得把人给憋死啊。

那分布式版本控制系统与集中式版本控制系统有何不同呢？首先，分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

和集中式版本控制系统相比，分布式版本控制系统的安全性要高很多，因为每个人电脑里都有完整的版本库，某一个人的电脑坏掉了不要紧，随便从其他人那里复制一个就可以了。而集中式版本控制系统的中央服务器要是出了问题，所有人都没法干活了。

在实际使用分布式版本控制系统的时候，其实很少在两人之间的电脑上推送版本库的修改，因为可能你们俩不在一个局域网内，两台电脑互相访问不了，也可能今天你的同事病了，他的电脑压根没有开机。因此，分布式版本控制系统通常也有一台充当“中央服务器”的电脑，但这个服务器的作用仅仅是用来方便“交换”大家的修改，没有它大家也一样干活，只是交换修改不方便而已。

![distributed-repo](C:\Users\15278\Desktop\typora\img\l-1712827168093-3.jpeg)

当然，Git的优势不单是不必联网这么简单，后面我们还会看到Git极其强大的分支管理，把SVN等远远抛在了后面。

<iframe id="aswift_6" name="aswift_6" style="left: 0px; top: 0px; border: 0px; width: 1200px; height: 0px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="1200" height="0" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-6727358730461554&amp;output=html&amp;h=280&amp;adk=1228093153&amp;adf=982595112&amp;w=1200&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1712827151&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=2183257665&amp;ad_type=text_image&amp;format=1200x280&amp;url=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896202780297248&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=1359&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;dt=1712827151465&amp;bpp=1&amp;bdt=1255&amp;idt=1&amp;shv=r20240409&amp;mjsv=m202404020101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D4e25a865b7c1ce49%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_MaEwsqVyulF9qENFFAArAWODQbtkQ&amp;gpic=UID%3D00000d2a92790e89%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_Makoj48xzmVXn03EqSuFWduGWS9OQ&amp;eo_id_str=ID%3D080f3d570f8fc833%3AT%3D1709777629%3ART%3D1712826913%3AS%3DAA-AfjY6uexMMmwPvP2Wacgm3DiX&amp;prev_fmts=300x600%2C300x600%2C336x280%2C336x280%2C336x280%2C0x0&amp;nras=2&amp;correlator=8128995671252&amp;frm=20&amp;pv=1&amp;ga_vid=1884912575.1712827151&amp;ga_sid=1712827151&amp;ga_hid=890784422&amp;ga_fc=0&amp;u_tz=480&amp;u_his=12&amp;u_h=1080&amp;u_w=1920&amp;u_ah=1032&amp;u_aw=1920&amp;u_cd=24&amp;u_sd=1&amp;adx=526&amp;ady=1364&amp;biw=1920&amp;bih=919&amp;scr_x=0&amp;scr_y=0&amp;eid=44759876%2C44759927%2C44759842%2C31082547%2C31082551%2C44795921%2C95329437%2C31082656%2C95322183&amp;oid=2&amp;pvsid=282793275832267&amp;tmod=1172027037&amp;uas=0&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896202815778784&amp;fc=384&amp;brdim=-8%2C-8%2C-8%2C-8%2C1920%2C0%2C1936%2C1048%2C1920%2C919&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1.01&amp;ifi=7&amp;uci=a!7&amp;btvi=6&amp;fsb=1&amp;dtd=4" data-google-container-id="a!7" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="COPHva_quYUDFRIWewcdM_YL9w" data-load-complete="true"></iframe>

CVS作为最早的开源而且免费的集中式版本控制系统，直到现在还有不少人在用。由于CVS自身设计的问题，会造成提交文件不完整，版本库莫名其妙损坏的情况。同样是开源而且免费的SVN修正了CVS的一些稳定性问题，是目前用得最多的集中式版本库控制系统。

除了免费的外，还有收费的集中式版本控制系统，比如IBM的ClearCase（以前是Rational公司的，被IBM收购了），特点是安装比Windows还大，运行比蜗牛还慢，能用ClearCase的一般是世界500强，他们有个共同的特点是财大气粗，或者人傻钱多。

微软自己也有一个集中式版本控制系统叫VSS，集成在Visual Studio中。由于其反人类的设计，连微软自己都不好意思用了。

分布式版本控制系统除了Git以及促使Git诞生的BitKeeper外，还有类似Git的Mercurial和Bazaar等。这些分布式版本控制系统各有特点，但最快、最简单也最流行的依然是Git！

### 安装Git

最早Git是在Linux上开发的，很长一段时间内，Git也只能在Linux和Unix系统上跑。不过，慢慢地有人把它移植到了Windows上。现在，Git可以在Linux、Unix、Mac和Windows这几大平台上正常运行了。

要使用Git，第一步当然是安装Git了。根据你当前使用的平台来阅读下面的文字：

#### 在Linux上安装Git

首先，你可以试着输入`git`，看看系统有没有安装Git：

```
$ git
The program 'git' is currently not installed. You can install it by typing:
sudo apt-get install git
```

像上面的命令，有很多Linux会友好地告诉你Git没有安装，还会告诉你如何安装Git。

如果你碰巧用Debian或Ubuntu Linux，通过一条`sudo apt-get install git`就可以直接完成Git的安装，非常简单。

老一点的Debian或Ubuntu Linux，要把命令改为`sudo apt-get install git-core`，因为以前有个软件也叫GIT（GNU Interactive Tools），结果Git就只能叫`git-core`了。由于Git名气实在太大，后来就把GNU Interactive Tools改成`gnuit`，`git-core`正式改为`git`。

如果是其他Linux版本，可以直接通过源码安装。先从Git官网下载源码，然后解压，依次输入：`./config`，`make`，`sudo make install`这几个命令安装就好了。

#### 在Mac OS X上安装Git

如果你正在使用Mac做开发，有两种安装Git的方法。

一是安装homebrew，然后通过homebrew安装Git，具体方法请参考homebrew的文档：http://brew.sh/。

第二种方法更简单，也是推荐的方法，就是直接从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode，选择菜单“Xcode”->“Preferences”，在弹出窗口中找到“Downloads”，选择“Command Line Tools”，点“Install”就可以完成安装了。

![install-git-by-xcode](C:\Users\15278\Desktop\typora\img\0-1712827196036-8.jpeg)

Xcode是Apple官方IDE，功能非常强大，是开发Mac和iOS App的必选装备，而且是免费的！

<iframe id="aswift_6" name="aswift_6" style="left: 0px; top: 0px; border: 0px; width: 1200px; height: 0px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="1200" height="0" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-6727358730461554&amp;output=html&amp;h=280&amp;adk=1228093153&amp;adf=982595112&amp;w=1200&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1712827176&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=2183257665&amp;ad_type=text_image&amp;format=1200x280&amp;url=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896067074338496&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=1359&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;dt=1712827175341&amp;bpp=1&amp;bdt=2076&amp;idt=2&amp;shv=r20240409&amp;mjsv=m202404080101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D4e25a865b7c1ce49%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_MaEwsqVyulF9qENFFAArAWODQbtkQ&amp;gpic=UID%3D00000d2a92790e89%3AT%3D1709777629%3ART%3D1712826913%3AS%3DALNI_Makoj48xzmVXn03EqSuFWduGWS9OQ&amp;eo_id_str=ID%3D080f3d570f8fc833%3AT%3D1709777629%3ART%3D1712826913%3AS%3DAA-AfjY6uexMMmwPvP2Wacgm3DiX&amp;prev_fmts=300x600%2C300x600%2C336x280%2C336x280%2C336x280%2C0x0&amp;nras=2&amp;correlator=1821226154650&amp;frm=20&amp;pv=1&amp;ga_vid=398705761.1712827174&amp;ga_sid=1712827174&amp;ga_hid=829625657&amp;ga_fc=0&amp;u_tz=480&amp;u_his=13&amp;u_h=1080&amp;u_w=1920&amp;u_ah=1032&amp;u_aw=1920&amp;u_cd=24&amp;u_sd=1&amp;adx=526&amp;ady=1225&amp;biw=1920&amp;bih=919&amp;scr_x=0&amp;scr_y=0&amp;eid=44759875%2C44759926%2C44759837%2C31082547%2C95326317%2C95329437%2C31082630%2C95320378&amp;oid=2&amp;pvsid=3411027525609904&amp;tmod=336970542&amp;uas=0&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896202780297248&amp;fc=384&amp;brdim=-8%2C-8%2C-8%2C-8%2C1920%2C0%2C1936%2C1048%2C1920%2C919&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1.01&amp;ifi=7&amp;uci=a!7&amp;btvi=6&amp;fsb=1&amp;dtd=1648" data-google-container-id="a!7" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="CJaR07vquYUDFQ4tewcduIYPlw" data-load-complete="true"></iframe>

#### 在Windows上安装Git

在Windows上使用Git，可以从Git官网直接[下载安装程序](https://git-scm.com/downloads)，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![install-git-on-windows](C:\Users\15278\Desktop\typora\img\0-1712827196036-9.jpeg)

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。你也许会担心，如果有人故意冒充别人怎么办？这个不必担心，首先我们相信大家都是善良无知的群众，其次，真的有冒充的也是有办法可查的。

注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。



#### 创建版本库

什么是版本库呢？版本库又名仓库，英文名**repository**，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

所以，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

```
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
```

`pwd`命令用于显示当前目录。在我的Mac上，这个仓库位于`/Users/michael/learngit`。

 如果你使用Windows系统，为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文。

第二步，通过`git init`命令把这个目录变成Git可以管理的仓库：

```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```

瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），细心的读者可以发现当前目录下多了一个`.git`的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。

如果你没有看到`.git`目录，那是因为这个目录默认是隐藏的，用`ls -ah`命令就可以看见。

也不一定必须在空目录下创建Git仓库，选择一个已经有东西的目录也是可以的。不过，不建议你使用自己正在开发的公司项目来学习Git，否则造成的一切后果概不负责。

<iframe id="aswift_6" name="aswift_6" style="left: 0px; top: 0px; border: 0px; width: 1200px; height: 0px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="1200" height="0" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-6727358730461554&amp;output=html&amp;h=280&amp;adk=1228093153&amp;adf=2211980168&amp;w=1200&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1712827224&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=2183257665&amp;ad_type=text_image&amp;format=1200x280&amp;url=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896827951938304&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=1359&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;dt=1712827224487&amp;bpp=2&amp;bdt=1183&amp;idt=-M&amp;shv=r20240409&amp;mjsv=m202404020101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D4e25a865b7c1ce49%3AT%3D1709777629%3ART%3D1712827223%3AS%3DALNI_MaEwsqVyulF9qENFFAArAWODQbtkQ&amp;gpic=UID%3D00000d2a92790e89%3AT%3D1709777629%3ART%3D1712827224%3AS%3DALNI_Makoj48xzmVXn03EqSuFWduGWS9OQ&amp;eo_id_str=ID%3D080f3d570f8fc833%3AT%3D1709777629%3ART%3D1712827224%3AS%3DAA-AfjY6uexMMmwPvP2Wacgm3DiX&amp;prev_fmts=300x600%2C300x600%2C0x0&amp;nras=2&amp;correlator=5332848376418&amp;frm=20&amp;pv=1&amp;ga_vid=1486473349.1712827224&amp;ga_sid=1712827224&amp;ga_hid=1371473987&amp;ga_fc=0&amp;u_tz=480&amp;u_his=14&amp;u_h=1080&amp;u_w=1920&amp;u_ah=1032&amp;u_aw=1920&amp;u_cd=24&amp;u_sd=1&amp;adx=526&amp;ady=1389&amp;biw=1920&amp;bih=919&amp;scr_x=0&amp;scr_y=0&amp;eid=44759876%2C44759927%2C44759842%2C31082547%2C42531705%2C42532242%2C44795922%2C95326315%2C95329436%2C31082656%2C95322329%2C31081717&amp;oid=2&amp;pvsid=421543658976100&amp;tmod=560938923&amp;uas=0&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896067074338496&amp;fc=384&amp;brdim=-8%2C-8%2C-8%2C-8%2C1920%2C0%2C1936%2C1048%2C1920%2C919&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1.01&amp;ifi=7&amp;uci=a!7&amp;btvi=3&amp;fsb=1&amp;dtd=16" data-google-container-id="a!7" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="COGap9LquYUDFfaCuQUdGg8N6Q" data-load-complete="true"></iframe>

#### 把文件添加到版本库

首先这里再明确一下，所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。

不幸的是，Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的，前面我们举的例子只是为了演示，如果要真正使用版本控制系统，就要以纯文本方式编写文件。

因为文本是有编码的，比如中文有常用的GBK编码，日文有Shift_JIS编码，如果没有历史遗留问题，强烈建议使用标准的UTF-8编码，所有语言使用同一种编码，既没有冲突，又被所有平台所支持。

使用Windows的童鞋要特别注意：

千万不要使用Windows自带的**记事本**编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载[Visual Studio Code](https://code.visualstudio.com/)代替记事本，不但功能强大，而且免费！

言归正传，现在我们编写一个`readme.txt`文件，内容如下：

```
Git is a version control system.
Git is free software.
```

一定要放到`learngit`目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。

<iframe id="aswift_7" name="aswift_7" style="left: 0px; top: 0px; border: 0px; width: 1200px; height: 0px;" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" width="1200" height="0" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" src="https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-6727358730461554&amp;output=html&amp;h=280&amp;adk=1228093153&amp;adf=277841169&amp;w=1200&amp;fwrn=4&amp;fwrnh=100&amp;lmt=1712827224&amp;num_ads=1&amp;rafmt=1&amp;armr=3&amp;sem=mc&amp;pwprc=2183257665&amp;ad_type=text_image&amp;format=1200x280&amp;url=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896827951938304&amp;fwr=0&amp;pra=3&amp;rh=200&amp;rw=1359&amp;rpe=1&amp;resp_fmts=3&amp;wgl=1&amp;fa=27&amp;dt=1712827224487&amp;bpp=2&amp;bdt=1183&amp;idt=2&amp;shv=r20240409&amp;mjsv=m202404020101&amp;ptt=9&amp;saldr=aa&amp;abxe=1&amp;cookie=ID%3D4e25a865b7c1ce49%3AT%3D1709777629%3ART%3D1712827223%3AS%3DALNI_MaEwsqVyulF9qENFFAArAWODQbtkQ&amp;gpic=UID%3D00000d2a92790e89%3AT%3D1709777629%3ART%3D1712827224%3AS%3DALNI_Makoj48xzmVXn03EqSuFWduGWS9OQ&amp;eo_id_str=ID%3D080f3d570f8fc833%3AT%3D1709777629%3ART%3D1712827224%3AS%3DAA-AfjY6uexMMmwPvP2Wacgm3DiX&amp;prev_fmts=300x600%2C300x600%2C0x0%2C1200x280&amp;nras=3&amp;correlator=5332848376418&amp;frm=20&amp;pv=1&amp;ga_vid=1486473349.1712827224&amp;ga_sid=1712827224&amp;ga_hid=1371473987&amp;ga_fc=0&amp;u_tz=480&amp;u_his=14&amp;u_h=1080&amp;u_w=1920&amp;u_ah=1032&amp;u_aw=1920&amp;u_cd=24&amp;u_sd=1&amp;adx=526&amp;ady=2236&amp;biw=1920&amp;bih=919&amp;scr_x=0&amp;scr_y=0&amp;eid=44759876%2C44759927%2C44759842%2C31082547%2C42531705%2C42532242%2C44795922%2C95326315%2C95329436%2C31082656%2C95322329%2C31081717&amp;oid=2&amp;pvsid=421543658976100&amp;tmod=560938923&amp;uas=0&amp;nvt=1&amp;ref=https%3A%2F%2Fwww.liaoxuefeng.com%2Fwiki%2F896043488029600%2F896067074338496&amp;fc=384&amp;brdim=-8%2C-8%2C-8%2C-8%2C1920%2C0%2C1936%2C1048%2C1920%2C919&amp;vis=1&amp;rsz=%7C%7Cs%7C&amp;abl=NS&amp;fu=128&amp;bc=31&amp;bz=1.01&amp;ifi=8&amp;uci=a!8&amp;btvi=4&amp;fsb=1&amp;dtd=22" data-google-container-id="a!8" tabindex="0" title="Advertisement" aria-label="Advertisement" data-google-query-id="CJHRp9LquYUDFa8tewcdMNAB8A" data-load-complete="true"></iframe>

和把大象放到冰箱需要3步相比，把一个文件放到Git仓库只需要两步。

第一步，用命令`git add`告诉Git，把文件添加到仓库：

```
$ git add readme.txt
```

执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令`git commit`告诉Git，把文件提交到仓库：

```
$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```

简单解释一下`git commit`命令，`-m`后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

嫌麻烦不想输入`-m "xxx"`行不行？确实有办法可以这么干，但是强烈不建议你这么干，因为输入说明对自己对别人阅读都很重要。实在不想输入说明的童鞋请自行Google，我不告诉你这个参数。

`git commit`命令执行成功后会告诉你，`1 file changed`：1个文件被改动（我们新添加的readme.txt文件）；`2 insertions`：插入了两行内容（readme.txt有两行内容）。

为什么Git添加文件需要`add`，`commit`一共两步呢？因为`commit`可以一次提交很多文件，所以你可以多次`add`不同的文件，比如：

```
$ git add file1.txt
$ git add file2.txt file3.txt
$ git commit -m "add 3 files."
```

## 时光机穿梭

我们已经成功地添加并提交了一个readme.txt文件，现在，是时候继续工作了，于是，我们继续修改readme.txt文件，改成如下内容：

```
Git is a distributed version control system.
Git is free software.
```

现在，运行`git status`命令看看结果：

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，`readme.txt`被修改过了，但还没有准备提交的修改。

虽然Git告诉我们`readme.txt`被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的`readme.txt`，所以，需要用`git diff`这个命令看看：

```
$ git diff readme.txt 
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个`distributed`单词。

知道了对`readme.txt`作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是`git add`：

```
$ git add readme.txt
```

同样没有任何输出。在执行第二步`git commit`之前，我们再运行`git status`看看当前仓库的状态：

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   readme.txt
```

`git status`告诉我们，将要被提交的修改包括`readme.txt`，下一步，就可以放心地提交了：

```
$ git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
```

提交后，我们再用`git status`命令看看仓库的当前状态：

```
$ git status
On branch master
nothing to commit, working tree clean
```

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working tree clean）的。

### 版本退回

现在，你已经学会了修改文件，然后把修改提交到Git版本库，现在，再练习一次，修改readme.txt文件如下：

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

然后尝试提交：

```
$ git add readme.txt
$ git commit -m "append GPL"
[master 1094adb] append GPL
 1 file changed, 1 insertion(+), 1 deletion(-)
```

像这样，你不断对文件进行修改，然后不断提交修改到版本库里，就好比玩RPG游戏时，每通过一关就会自动把游戏状态存盘，如果某一关没过去，你还可以选择读取前一关的状态。有些时候，在打Boss之前，你会手动存盘，以便万一打Boss失败了，可以从最近的地方重新开始。Git也是一样，每当你觉得文件修改到一定程度的时候，就可以“保存一个快照”，这个快照在Git中被称为`commit`。一旦你把文件改乱了，或者误删了文件，还可以从最近的一个`commit`恢复，然后继续工作，而不是把几个月的工作成果全部丢失。

现在，我们回顾一下`readme.txt`文件一共有几个版本被提交到Git仓库里了：

版本1：wrote a readme file

```
Git is a version control system.
Git is free software.
```

版本2：add distributed

```
Git is a distributed version control system.
Git is free software.
```

版本3：append GPL

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

当然了，在实际工作中，我们脑子里怎么可能记得一个几千行的文件每次都改了什么内容，不然要版本控制系统干什么。版本控制系统肯定有某个命令可以告诉我们历史记录，在Git中，我们用`git log`命令查看：

```
$ git log
commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -> master)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

commit e475afc93c209a690c39c13a46716e8fa000c366
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

`git log`命令显示从最近到最远的提交日志，我们可以看到3次提交，最近的一次是`append GPL`，上一次是`add distributed`，最早的一次是`wrote a readme file`。

如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数：

```
$ git log --pretty=oneline
1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -> master) append GPL
e475afc93c209a690c39c13a46716e8fa000c366 add distributed
eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0 wrote a readme file
```

需要友情提示的是，你看到的一大串类似`1094adb...`的是`commit id`（版本号），和SVN不一样，Git的`commit id`不是1，2，3……递增的数字，而是一个SHA1计算出来的一个非常大的数字，用十六进制表示，而且你看到的`commit id`和我的肯定不一样，以你自己的为准。为什么`commit id`需要用这么一大串数字表示呢？因为Git是分布式的版本控制系统，后面我们还要研究多人在同一个版本库里工作，如果大家都用1，2，3……作为版本号，那肯定就冲突了。

每提交一个新版本，实际上Git就会把它们自动串成一条时间线。如果使用可视化工具查看Git历史，就可以更清楚地看到提交历史的时间线：

![0](./0.jpg)

好了，现在我们启动时光穿梭机，准备把`readme.txt`回退到上一个版本，也就是`add distributed`的那个版本，怎么做呢？

首先，Git必须知道当前版本是哪个版本，在Git中，用`HEAD`表示当前版本，也就是最新的提交`1094adb...`（注意我的提交ID和你的肯定不一样），上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。

现在，我们要把当前版本`append GPL`回退到上一个版本`add distributed`，就可以使用`git reset`命令：

```
$ git reset --hard HEAD^
HEAD is now at e475afc add distributed
```

`--hard`参数有啥意义？这个后面再讲，现在你先放心使用。

看看`readme.txt`的内容是不是版本`add distributed`：

```
$ cat readme.txt
Git is a distributed version control system.
Git is free software.
```

果然被还原了。

还可以继续回退到上一个版本`wrote a readme file`，不过且慢，让我们用`git log`再看看现在版本库的状态：

```
$ git log
commit e475afc93c209a690c39c13a46716e8fa000c366 (HEAD -> master)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

最新的那个版本`append GPL`已经看不到了！好比你从21世纪坐时光穿梭机来到了19世纪，想再回去已经回不去了，肿么办？

办法其实还是有的，只要上面的命令行窗口还没有被关掉，你就可以顺着往上找啊找啊，找到那个`append GPL`的`commit id`是`1094adb...`，于是就可以指定回到未来的某个版本：

```
$ git reset --hard 1094a
HEAD is now at 83b0afe append GPL
```

版本号没必要写全，前几位就可以了，Git会自动去找。当然也不能只写前一两位，因为Git可能会找到多个版本号，就无法确定是哪一个了。

再小心翼翼地看看`readme.txt`的内容：

```
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

果然，我胡汉三又回来了。

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的`HEAD`指针，当你回退版本的时候，Git仅仅是把HEAD从指向`append GPL`：

![image-20240423163947015](./image-20240423163947015.png)

改为指向`add distributed`：

![image-20240423163958451](./image-20240423163958451.png)

然后顺便把工作区的文件更新了。所以你让`HEAD`指向哪个版本号，你就把当前版本定位在哪。

现在，你回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本怎么办？找不到新版本的`commit id`怎么办？

在Git中，总是有后悔药可以吃的。当你用`$ git reset --hard HEAD^`回退到`add distributed`版本时，再想恢复到`append GPL`，就必须找到`append GPL`的commit id。Git提供了一个命令`git reflog`用来记录你的每一次命令：

```
$ git reflog
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file
```

终于舒了口气，从输出可知，`append GPL`的commit id是`1094adb`，现在，你又可以乘坐时光机回到未来了。

### 工作区和暂存区

Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念。

先来看名词解释。

#### 工作区（Working Directory）

就是你在电脑里能看到的目录，比如我的`learngit`文件夹就是一个工作区：

#### 版本库（Repository）

工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`。

![0](./0-1713861723147-2.jpg)

分支和`HEAD`的概念我们以后再讲。

前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：

第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。

因为我们创建Git版本库时，Git自动为我们创建了唯一一个`master`分支，所以，现在，`git commit`就是往`master`分支上提交更改。

你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。

俗话说，实践出真知。现在，我们再练习一遍，先对`readme.txt`做个修改，比如加上一行内容：

```
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
```

然后，在工作区新增一个`LICENSE`文本文件（内容随便写）。

先用`git status`查看一下状态：

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	LICENSE

no changes added to commit (use "git add" and/or "git commit -a")
```

Git非常清楚地告诉我们，`readme.txt`被修改了，而`LICENSE`还从来没有被添加过，所以它的状态是`Untracked`。

现在，使用两次命令`git add`，把`readme.txt`和`LICENSE`都添加后，用`git status`再查看一下：

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   LICENSE
	modified:   readme.txt
```

现在，暂存区的状态就变成这样了：

![0](./0-1713862055712-4.jpg)

所以，`git add`命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行`git commit`就可以一次性把暂存区的所有修改提交到分支。

```
$ git commit -m "understand how stage works"
[master e43a48b] understand how stage works
 2 files changed, 2 insertions(+)
 create mode 100644 LICENSE
```

一旦提交后，如果你又没有对工作区做任何修改，那么工作区就是“干净”的：

```
$ git status
On branch master
nothing to commit, working tree clean
```

现在版本库变成了这样，暂存区就没有任何内容了：

![0](./C:/Users/15278/AppData/Local/Temp/0.jpg)