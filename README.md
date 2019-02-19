# moon
## WYSIWYG
>>今天完成了nopcommerce购物平台的搭建与发布，趁这个时间做一下复盘工作
### 准备工具
>>* iis
>>* visual studio
>>* sql server2008 / 2012
>>* nopcommerce_3.20_nosource

### 搭建`nopcommerce_nosource`
>>起初想使用最新版nopcommerce，但是发现新版本有一些问题，所以选择的3.20版本而没有用目前最新的4.10。<br>
>>事先搭建数据库，我下载了2008的sql数据库，2012版本的也可以，但是08版本更方便点，高版本数据库用vs无法连接，我的vs是2017版本<br>
>>以4.10_source为例，使用vs打开后正常安装，但是4.10_source在iis上发布的时候我出现的是dir页面，因为要求也是无源码安装，所以后期也没有仔细研究怎么才会出现访问页面。<br>
>>而4.10_nosource在vs上无法加载内容，换成classic 4 版本也无法使用。后期换成4.0_nosource也没用，干脆下载了3.20版本的无源码安装文件，接下来说下过程。网上都有，但是太多了，所以整理下免得以后耗费时间去找<br>
>>#### 安装
>>可以从[此处](https://github.com/nopSolutions/nopCommerce/releases?after=release-3.60)下载nopcommerce_3.20_nosource文件.<br>
>>下载完成后，使用vs打开网站，选择nopcommerce_3.20_nosource,右击解决方案，选择重新生成解决方案，完成后点击iis express运行网站。<br>
>>iis 添加网站，网站命名nopcommerce_3.20_nosource以便区分，物理地址选中nopcommerce_3.20_nosource所在位置，端口选择一个空的就可以。<br>
>>iis 内选中网站，在nopcommerce_3.20_nosource主页内双击目录浏览，最右侧栏选择启用。此时已经可以启用，右击网站，选择管理网站，没有启用网站的选择启动，启动后点击浏览，此时就可以在浏览器中进入安装目录(vs打开也可以进入安装目录)<br>
>>设置账号密码，重点在于数据库设置上。此时打开 MICROSOFT SQL SERVER MANAGEMENT STUDIO,选择刚刚创建的数据库，右击-属性-查看连接属性，记录服务器名称与数据库名称。数据库登陆可以选择'.'登陆，也可以设置其他账户登陆，例如sa账户。设置完成后点击安装。
### 发布网站
>>将nopcommerce放到iis上后，基本就可以在内网访问了，但是想要外网访问的话，还需要做一下内网穿透工作。<br>
>>在这里我使用的花生壳内网穿透，需要注意的是设置里面需要注意IP地址。设置为动态的话以后就要随着网络的变更而手动更改，设置成静态的话就无法连接网络。<br>
