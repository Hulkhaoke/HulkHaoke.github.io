&#160; &#160; &#160; &#160;在安装Ubuntu后，重启选择Windows 10系统，突然发现系统时间比实际时间慢了八个小时。当时我乐了，难不成这系统傻了定位识别我还在英国？检查设置后确认时区设置是东八区没问题，联网更新时间后恢复了正常。但之后的几天每当我先打开Ubuntu再打开Windows就会发现时间依然不对，上网查询后发现原来是由于两个系统对时间的识别方式不同造成的。

&#160; &#160; &#160; &#160;Ubuntu 默认硬件时间为UTC（Coordinated Universal Time）即协调世界时，中国时间为UTC+8；而Windows则认定硬件时间为系统时间。这就造成了当先开启Ubuntu系统时，系统从网络得到本地时间例如为8点钟，然后其修改硬件时间为0点，再次启用Windows时，Windows读取硬件时间为本地时间，这就造成了系统显示时间比实际时间慢8小时的问题。

&#160; &#160; &#160; &#160;目前通用的解决方法有两种：一种是修改Ubuntu系统时间的读取方式，另一种是修改Windows系统时间的读取方式。在此推荐修改Ubuntu系统，因为修改方式极其简单。
&#160; &#160; &#160; &#160;在终端输入：

```
#安装时间校准服务
$ sudo apt-get install ntpdate
#从time.windows.com获取本地时间
$ sudo ntpdate time.windows.com
#同步时间到硬件
$ sudo hwclock --localtime --systohc
```
&#160; &#160; &#160; &#160;运行结果如图一所示：


![修改Ubuntu系统时间的认定方式](http://img.blog.csdn.net/20170629142617247?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图一：修改Ubuntu系统时间的认定方式