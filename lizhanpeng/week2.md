# 基本运行步骤
* 1 DNS解析

* 2 TCP连接

* 3 发送HTTP请求

* 4 服务器处理请求

* 5 返回响应结果

* 6  关闭TCP连接 

* 7 浏览器解析HTML并且进行布局渲染

在网页中输入网址后，首先是由DNS解析域名，将域名解析成对应的服务器IP地址,得到服务器IP地址后就进行链接到该服务器的操作，即客户端与服务器的TCP链接，有一个说法叫“三次握手”，客户端发送一个带有SYN标志的数据包给服务端，服务端收到后，回传一个带有SYN/ACK标志的数据包以示传达确认信息，最后客户端再回传一个带ACK标志的数据包，代表握手结束，连接成功.下面是网上嫖来的图:
![2](https://img-blog.csdn.net/20171228115620921)
0000 与服务器建立了连接后，就可以向服务器发起请求了,（反正就是发送请求，具体的我也不知道怎么弄得），然后就是服务器处理请求，服务器端收到请求后的由http服务器处理请求,web服务器解析用户请求，知道了需要调度哪些资源文件，再通过相应的这些资源文件处理用户请求和参数，并调用数据库信息，最后将结果通过web服务器返回给浏览器客户端。
最重要的差不多就只有这么一些吧，主要是做网页时间花太久了，没怎么深入了解这些，以后我会去深入了解这方面的内容的。。。
http://www.reader-patarw.club/ ！！！`要把网页缩放至80%最好`
