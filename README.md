# moon
## WYSIWYG
# 1.平台`搭建`与`发布`

## `nopcommerce`

今天完成了nopcommerce购物平台的`基础搭建`与`发布`，趁这个时间做一下复盘工作

#### 准备工具
* iis
* visual studio
* sql server2008 / 2012
* nopcommerce_3.20_nosource

#### 搭建`nopcommerce_nosource`

起初想使用最新版nopcommerce，但是发现新版本有一些问题，所以选择的3.20版本而没有用目前最新的4.10。<br>

事先搭建数据库，我下载了2008的sql数据库，2012版本的也可以，但是08版本更方便点，高版本数据库用vs无法连接，我的vs是2017版本<br>

以4.10_source为例，使用vs打开后正常安装，但是4.10_source在iis上发布的时候我出现的是dir页面，因为要求也是无源码安装，所以后期也没有仔细研究怎么才会出现访问页面。<br>

而4.10_nosource在vs上无法加载内容，换成classic 4 版本也无法使用。后期换成4.0_nosource也没用，干脆下载了3.20版本的无源码安装文件，接下来说下过程。网上都有，但是太多了，所以整理下免得以后耗费时间去找<br>

#### 安装

可以从[此处](https://github.com/nopSolutions/nopCommerce/releases?after=release-3.60)下载nopcommerce_3.20_nosource文件.<br>

下载完成后，使用vs打开网站，选择nopcommerce_3.20_nosource,右击解决方案，选择重新生成解决方案，完成后点击iis express运行网站。<br>

iis 添加网站，网站命名nopcommerce_3.20_nosource以便区分，物理地址选中nopcommerce_3.20_nosource所在位置，端口选择一个空的就可以。<br>

iis 内选中网站，在nopcommerce_3.20_nosource主页内双击目录浏览，最右侧栏选择启用。此时已经可以启用，右击网站，选择管理网站，没有启用网站的选择启动，启动后点击浏览，此时就可以在浏览器中进入安装目录(vs打开也可以进入安装目录)<br>

设置账号密码，重点在于数据库设置上。此时打开 MICROSOFT SQL SERVER MANAGEMENT STUDIO,选择刚刚创建的数据库，右击-属性-查看连接属性，记录服务器名称与数据库名称。数据库登陆可以选择'.'登陆，也可以设置其他账户登陆，例如sa账户。设置完成后点击安装。
#### 发布网站

将nopcommerce放到iis上后，基本就可以在内网访问了，但是想要外网访问的话，还需要做一下内网穿透工作。<br>


#### 总结

整体感觉还行，关于要去做内网穿透，今天总算完成了固定IP地址的设定，还不错，把IP地址设置为`127.0.0.1`就可以不用那么繁琐的去修改了，下次只需要在电脑商直接运行就可以开启网站服务，个人测试用足够了，如果想看看成果，可以[点击这里试试](https://salamander.imdo.co/) , 文件在此处，可以[点击下载](https://pan.baidu.com/s/1HKPFsTvrWvsxL6oHIpaIgw).<br>

# `umbraco`

今天完成了umbraco新闻网站的制作, 当然也是在[博客内](https://www.cnblogs.com/haijd/p/Umbraco-Getting-Started-7.html)找到的为数不多的教程, 虽然是手抄了一遍, 但是也是很多麻烦, 见笑. 现在在这里对umbraco的搭建做一下复盘工作

#### 准备工具
* visual studio
* UmbracoCms.7.13.1

#### 搭建`UmbracoCms.7.13.1`

想要下载的话可以[点击下载](https://github.com/stannauyiel/moon/tree/master/UmbracoCms.7.13.1_%E6%96%B0%E9%97%BB%E7%BD%91%E7%AB%99%E5%88%B6%E4%BD%9C)我已经做好的文件, 使用visual studio打开网站即可.

如果想从头开始做, 可以进入官网下载文件, 有云端文件, 但是由于经费问题所以只能托管在本机上(感叹一句有钱真好，云随便买。。。), 无语的是wifi每隔一段时间断一次, 所以不打算做外网连接了.

下载完成打开登陆都没什么问题, 了解 umbraco 的结构以及使用规则是重点.

### 有问题可以联系邮箱`stan142857@gmail.com`.<br>

## 2.问题与解决

### 问题一 : nopcommerce 图片加载延迟<br>

 `外网进入`，加载延迟<br><img src="https://github.com/stannauyiel/moon/blob/master/pictures/High%20delay%2C%20unable%20to%20load.png" width="475" height="250"/><br>

`本地查看`，正常加载<br>
<img src="https://github.com/stannauyiel/moon/blob/master/pictures/Images_of_normal.png" width="475" height="250"/><br>
* 解决：[点击以查看解决方案](https://www.cnblogs.com/EntityFramework/articles/2918510.html)，此内容比较多，需要整理<br>
