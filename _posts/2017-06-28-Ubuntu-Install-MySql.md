&#160; &#160; &#160; &#160;在终端输入代码，如下：

```
# 下载安装MySQL服务
$ sudo apt-get install mysql-server

```
&#160; &#160; &#160; &#160;下载安装时会出现要求设置密码的界面，如图一所示：

![MySQL安装](http://img.blog.csdn.net/20170630130737917?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

 图一：安装时出现的界面

&#160; &#160; &#160; &#160;一般建议设置密码后再按Enter确认，如果直接Enter确认进入，则默认root用户的密码为空：
![安装结束](http://img.blog.csdn.net/20170630130946606?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图二：安装服务结束

&#160; &#160; &#160; &#160;接下来继续输入：
```
# 下载安装MySQL客户端
$ sudo apt-get isntall mysql-client
# 下载安装MySQL开发接口
$ sudo apt-get install libmysqlclient-dev
```
&#160; &#160; &#160; &#160;待安装完成后可运行以下代码检查是否成功安装MySQL：

```
$ sudo netstat -tap|grep mysql

```
&#160; &#160; &#160; &#160;若成功安装，则应当显示如下，MySQL端口处于LISTEN状态：

![成功安装](http://img.blog.csdn.net/20170630131934617?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图三：成功安装MySQL

&#160; &#160; &#160; &#160;登陆MySQL的方法为：

```
$ sudo mysql -u root -p
```
&#160; &#160; &#160; &#160;终端上会要求你输入password，如果上一步设置了密码，就填那个；如果上一步直接Enter跳过，那么密码就为空，即Enter。切记，如果没有设置密码，则必须以管理员身份运行，即前面加上 sudo，否则会出现 ERROR 1698 的情况，如图五所示。
&#160; &#160; &#160; &#160;下图为登陆成功的界面：

![登陆成功](http://img.blog.csdn.net/20170630143251777?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图四：登陆成功

&#160; &#160; &#160; &#160;登陆失败：

![登陆失败](http://img.blog.csdn.net/20170630144136379?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图五：没有设置密码，并且没有以 sudo 运行导致登陆失败
