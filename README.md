<h1 align="center">电视壳子（ShellTV）</h1>
<img src="./images/shelltv.png" alt="My Image" width="100"/>


- [关于此项目](#-关于此项目)
- [对源配置文件语法的补充定义](#️-对源配置文件语法的补充定义)
- [界面截图](#-界面截图)
- [玩法](#-玩法)
- [关于IPTV](#-关于iptv)
- [捐赠](#-捐赠)


---

## 📌 关于此项目
- 本项目修改自开源项目 https://github.com/CatVodTVOfficial/TVBoxOSC 在此致敬！🌹🌹🌹 
- 与原开源项目（TvBox）相比，本项目在功能上没有太多改进，主要是依个人喜好对操作体验进行了一些优化：
    - 增加基于影片的关联推荐，以及基于影人的关联推荐
    - 对数据源文件的语法定义进行了扩展，以更好处理影片元数据缺失问题（如海报等）
    - 直播节目收藏等其它一些功能
- 联系我们:  QQ_3877275490 ,邮件_3877275490@qq.com

--- 

## 🛠️ 对源配置文件语法扩展
为改进用户体验，**电视壳子**对TvBox项目的[源配置文件的语法定义](./tvbox源配置文件基本语法.md)进行了扩展，如果你是进阶玩家（致力于定制属于自己的配置文件），可以使用这些扩展定义，并配合**电视壳子**使用，以获取更好的使用体验（如，避免收藏与历史记录中出现大量无意义的海报，或反复打开已失效的阿里资源）。这些语法扩展多用于网盘搜索类、原数据无人维护的源。

以下是这些扩展语法的语义描述：

| 属性       | 描述                     | 缺省值   |
|------------|--------------------------|--------|
| hasPoster| 该源提供海报，1：提供，0：不提供  | 1 |
| hasMeaningfulTitle| 该源提供准确标题，1：提供，0：不提供| 1 |
| hasTags       | 该源提供影片的原数据，1：提供，0：不提供      | 1|
| checkAlipan       | 检查阿里资源的有效性，1：检查，0：不检查      | 0|

样例如下：
[源配置样例.json](./源配置样例.json)

--- 

## 📺 界面截图

### 主页

<img src="images/home.png" alt="Example Image" width="600" >

### 搜索页

<img src="images/fastSearch.png" alt="Example Image" width="600" >

### 详情页

<img src="images/detail.png" alt="Example Image" width="600" >**

### 影人关联

<img src="images/personage.png" alt="Example Image" width="600" >

--- 

## 🔑 玩法

#### 入门玩家
1. 百度或Github 搜索配置文件，复制URL地址，关键词：TVBox配置（最好先在电脑上试一下配置文件是否能正常下载，[这里](./source.md)是的几个网上搜索到的源，请自行确认其版权的合法性）。
2. 进入[APP配置源地址界面](./images/config.png) ➜ 直接输入URL地址或在[远程控制界面](./images/config_pc.png)中输入URL地址 ➜ 确定保存、退出


#### 进阶玩家 (指那些有定制需求的玩家)
1. 百度或Github 搜索、下载一个你基本满意的配置文件，作为模板（注，如果你想做全套，还要将这个源配置文件中索引的其它文件一并下载，如.jar和.m3u文件等）
2. 根据[基础语法](./tvbox源配置文件基本语法.md)和[扩展语法定义](#️-对源配置文件语法的补充定义)，对模板进行修改，包括，删除、排序或拼接等（注，修改过程中要确保其中的索引文件地址正确，你可能需要将原有的相对地址改为绝对地址，或将原有的绝对地址改为相对地址）
3. 获取机顶盒文件[存储权限](./images/rights.jpg)。
4. 将修改后的配置文件（.json）和相关的其它文件（.jar, .m3u）上传到机顶盒：打开[APP源配置界面](./images/config.png) ➜ [用电脑或手机连接](./images/config_pc.png) ➜ [创建一个文件夹](./images/folder.jpg)（如 shelltv） ➜ 将直播配置文件上传至该文件夹 ➜ [在APP源配置界面“源地址”一栏中填写正确地址](./images/source.png)（如，`http://localhost:9978/file/shelltv/源配置样例.json`，其中，shelltv是刚刚创建的方件夹，源配置样例.json是上传的配置文件、9978是[APP源配置界面](./images/config.png)上显示的端口号，“localhost”和“file”是固定的） ➜ 确定保存并退出。(一个测试以上配置是否正确的方法是，将上面地址输入到电脑浏览器的地址栏中，将localhost换成机顶盒的实际地址，应该可以下载这个文件)

--- 

## 📥 关于IPTV
**电视壳子**支持IPTV直播源，但是由于IPTV直播源的特殊性，我们不提供IPTV直播源的配置文件，用户可以按如下步骤自行搜索IPTV直播源的配置文件，然后上传到机顶盒中使用。

1.根据你所在地区和宽带提供商，在github或百度搜索并下载相应的IPTV组播地址文件，关键字：iptv 组播（比如 https://github.com/xisohi/IPTV-Multicast-source ）（一个测试你所找到的iptv组播地址是否可用的方法是：将其中一个ip地址输入电脑浏览器的地址栏，如 rtp://239.3.1.241:8000，看是否能正常播放。）

2.按以下两种格式中的一种修改、生成tvbox直播配置文件：[直播配置传统格式](./直播配置传统格式.m3u)（group-title标识分组）、[直播配置简化格式](./直播配置简化格式.m3u)（#EXTGENRE 标识分组）

3.获取机顶盒文件[存储权限](./images/rights.jpg)。

4.将修改后的配置文件（.m3u）上传到机顶盒：打开[APP源配置界面](./images/config.png) ➜ [用电脑或手机连接](./images/config_pc.png) ➜ [创建一个文件夹](./images/folder.jpg)（如 shelltv） ➜ 将直播配置文件上传至该文件夹 ➜ [在APP源配置界面“直播地址”一栏中填写正确地址](./images/iptv.png)（如，`http://localhost:9978/file/shelltv/直播配置.m3u`，其中shelltv是刚刚创建的方件夹，直播配置.m3u是上传的配置文件） ➜ 确定保存并退出。(一个测试以上配置是否正确的方法是，将上面地址输入到电脑浏览器的地址栏中，，将localhost换成机顶盒的实际地址，应该可以下载这个文件)

4.在**电视壳子**主页，点击直播，即可看到[直播节目](./images/broadcast.png)。（注意选择正确的播放器，通常是IJK）

5.如果你是进阶玩家，可以在[源配置文件（.json）](./源配置样例.json)中引用[直播配置文件（.m3u）](./直播配置传统格式.m3u)，无需另外配置直播文件。


## 🎉 捐赠
**电视壳子**部分特色功能依赖于服务器资源，为覆盖基本开销，我们接受捐赠。您的捐赠将用于云服务器的维护，并支持我们走得更远。

捐赠方式：应用首页  ➜  捐赠按钮

<img src="images/donation.png" alt="Example Image" width="600" >



