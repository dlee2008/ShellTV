<h1 align="center">电视壳子（ShellTV）</h1>

![Profile Views](https://komarev.com/ghpvc/?username=your-username&color=blue) ![Stars](https://img.shields.io/github/stars/your-username?style=social) ![Followers](https://img.shields.io/github/followers/your-username?style=social)


<h3 align="center">目  录</h1>

- [关于此项目](#-关于此项目)
- [对源配置文件语法的补充定义](#️-对源配置文件语法的补充定义)
- [界面截图](#-界面截图)
- [玩法](#-玩法)
- [关于IPTV](#-关于iptv)
- [捐赠](#-捐赠)

---

## 📌 关于此项目
- 本项目修改自开源项目 https://github.com/CatVodTVOfficial/TVBoxOSC 在此致敬！🌹🌹🌹 
- 本项目在功能上没有太多改进，主要对操作体验依个人喜好进行了优化 
- 增加基于影片的关联推荐，以及基于影人的关联推荐
- 对数据源文件的语法定义进行了扩展，以更好处理影片元数据缺失问题（如海报等）
- 直播节目收藏等其它一些功能
- 联系方式:  QQ 3877275490 [给我邮件](mailto:3877275490@qq.com)

--- 

## 🛠️ 对源配置文件语法的补充定义
为改进用户体验，**电视壳子**对TvBox项目的源配置文件的语法定义进行了扩展，如果你是进阶玩家（致力于定制属于自己的配置文件），可以使用这些扩展定义，并配合**电视壳子**使用，以获取更好的使用体验（如，避免收藏与历史记录中出现大量无意义的海报）。这些补充定义多用于网盘搜索类、原数据无人维护的源。

以下是这些扩展语法的语义描述：

| 属性       | 描述                     | 缺省值   |
|------------|--------------------------|--------|
| hasPoster| 该源提供海报，1：提供，0：不提供  | 1 |
| hasMeaningfulTitle| 该源提供准确标题，1：提供，0：不提供| 1 |
| hasTags       | 该源提供影片的原数据，1：提供，0：不提供      | 1|

样例如下：
[源配置样例.json](./源配置样例.json)

--- 

## 📺 界面截图

### 主页

<img src="images/home.png" alt="Example Image" width="600" >

### 搜索页

<img src="images/fastSearch.png" alt="Example Image" width="600" >

### 详情页

<img src="images/detail.png" alt="Example Image" width="600" >

### 影人关联

<img src="images/personage.png" alt="Example Image" width="600" >

--- 

## 🔑 玩法

#### 入门玩家
1. 百度或Github 配置文件,复制URL地址（最好先在电脑上试一下，是否能下载配置文件）
2. 进入APP配置源地址界面 ➜ 直接输入URL地址或[在远程控制界面中输入]() ➜ 确定、退出

#### 进阶玩家 (指那些有定制需求的玩家)
1. 百度或Github 下载一个你基本满意的配置文件，作为模板（注，如果你想做全套，还要将这个源配置文件中索引的其它文件一并下载，如.jar文件等）
2. 根据[基础语法]()和[补充语法定义](#️-对源配置文件语法的补充定义)，对模板进行修改，包括，删除、排序或拼接等（注，修改过程中要确保其中的索引文件地址正确，你可能需要将原有的相对地址改为绝对地址）
3. 将修改后的配置文件和相关的其它文件上传到机顶盒：打开[APP源配置界面](./images/config.png) ➜ [用电脑或手机连接](./images/config_pc.png) ➜ [创建一个文件夹](./images/folder.jpg)（如 shelltv） ➜ 将直播配置文件上传至该文件夹 ➜ [在APP源配置界面“源地址”一栏中填写正确地址](./images/source.png)（如，`http://localhost:9978/file/shelltv/源配置样例.json`，其中shelltv是刚刚创建的方件夹，源配置样例.json是上传的配置文件）、确定保存并退出。

--- 

## 📥 关于IPTV
电视壳子支持IPTV直播源，但是由于IPTV直播源的特殊性，我们不提供IPTV直播源的配置文件，用户可以按如下步骤自行搜索IPTV直播源的配置文件，然后上传到电视壳子中使用。

1.根据你所在地区和宽带提供商，在github或百度搜索并下载相应的IPTV组播地址文件，关键字：iptv 组播（比如 https://github.com/xisohi/IPTV-Multicast-source ）

2.按以下两种格式修改生成tvbox直播配置文件：[直播配置传统格式](./直播配置传统格式.m3u)（group-title标识分组）、[直播配置简化格式](./直播配置简化格式.m3u)（#EXTGENRE 标识分组）

3.打开[APP源配置界面](./images/config.png) ➜ [用电脑或手机连接](./images/config_pc.png) ➜ [创建一个文件夹](./images/folder.jpg)（如 shelltv） ➜ 将直播配置文件上传至该文件夹 ➜ [在APP源配置界面“直播地址”一栏中填写正确地址](./images/iptv.png)（如，`http://localhost:9978/file/shelltv/直播配置.m3u`，其中shelltv是刚刚创建的方件夹，直播配置.m3u是上传的配置文件）、确定保存并退出。

4.在电视壳子主页，点击直播，即可看到[直播节目](./images/broadcast.png)。（注意选择正确的播放器，通常是IJK）

5.如果你是进阶玩家，可以在源配置文件（.json）中引用直播配置文件（.m3u），无需要另外配置直播文件。


## 🎉 捐赠
由于**电视壳子**部分特色功能依赖于服务器资源，为覆盖基本开销，我们接受捐赠。您的捐赠将用于支付服务器费用、域名费用等。
方式：在应用首页，点击捐赠按钮

<img src="images/donation.png" alt="Example Image" width="600" >



