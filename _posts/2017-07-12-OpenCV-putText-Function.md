
&#160; &#160; &#160; &#160;在Python中，putText函数常用于在图像上绘图。其原型为：

```
cv2.putText(img, text, org, fontFace, fontScale, color)

#img – 想要打印上文字的图像
#text – 想要打印的文字
#org – 文字的左下角坐标
#fontFace – 字体，可选的有：FONT_HERSHEY_SIMPLEX, 
#		FONT_HERSHEY_PLAIN, FONT_HERSHEY_DUPLEX, 
#		FONT_HERSHEY_COMPLEX, FONT_HERSHEY_TRIPLEX, 
#		以及 FONT_HERSHEY_SCRIPT_COMPLEX, 其中任意一种字体
#		都可加上 FONT_ITALIC 使其变为斜体
#fontScale – 字号
#color – 颜色
```

&#160; &#160; &#160; &#160;下面是代码应用，具体代码将在文章最后展示。
&#160; &#160; &#160; &#160;用摄像头获取图像，并在图像上打印出 “Hello World！”。

![puText](http://img.blog.csdn.net/20170629175851485?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvSHVsa2hhb2tl/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图一：在图片上打印 “Hello World！”

Python代码：

```
import cv2

cap = cv2.VideoCapture(0)
while(cap.isOpened()):
    # read image
    ret, img = cap.read()
    # Display the text
    cv2.putText(img, "Hello World!", (50, 150), cv2.FONT_HERSHEY_SIMPLEX, 3, 1)
    # show appropriate images in windows
    cv2.imshow('putText', img)

    k = cv2.waitKey(10)
    if k == 27:
        break
```
