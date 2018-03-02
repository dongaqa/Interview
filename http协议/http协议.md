知识点：
1. HTTP的定义和主要特点，http1.0和1.1的区别
2. 交互流程
3. post和get的区别
4. url和uri的区别





## HTTP的定义和主要特点
HTTP，HyperText Transfer Protocol  超文本传输协议

1、简单快速：客户向服务器请求服务时，只需传送请求方法和路径。请求方法常用的有GET、HEAD、POST。每种方法规定了客户与服务器联系的类型不同。由于HTTP协议简单，使得HTTP服务器的程序规模小，因而通信速度很快。

2、灵活：HTTP允许传输任意类型的数据对象。正在传输的类型由Content-Type加以标记。

3.无连接：无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间。

4.无状态：HTTP协议是无状态协议。无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。另一方面，在服务器不需要先前信息时它的应答就较快。



## 客户端与服务器的交互过程
![](https://upload-images.jianshu.io/upload_images/2964446-5a35e17f298a48e1.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1. 客户端发起请求，连接服务器
2. 发送请求数据
3. 服务器收到请求数据，返回资源
4. 断开连接（具体哪一端主动断开连接？）

## URI与URL的区别
	
URI（Uniform Resource Identifier）  统一资源标识符
URL (Uniform Resource Locator)     统一资源定位符
URN (Uniform Resource Name)        统一资源名称

> URI = URL + URN

自己的理解：网络上每个资源都有自己的地址，有的是通过url（http://xxxx:80/aa/res.txt）去定位，有的是通过urn（特定的内容有唯一的名字）去定位，这两种方式加起来就是URI


###URL

http://www.aspxfans.com:8080/news/index.asp?boardID=5&ID=24618&page=1

格式： 
scheme：//host:port/location?参数1&参数2
HTTP默认的端口号为80，HTTPS默认的端口号为443



##协议格式

###请求部分

请求部分 = 请求行 + 请求头 + 请求体

请求行： <method> <url> <version>CRLF     CRLF代表回车符+换行符

![](https://upload-images.jianshu.io/upload_images/2964446-fdfb1a8fce8de946.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	GET /562f25980001b1b106000338.jpg HTTP/1.1
	Host    img.mukewang.com
	User-Agent    Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.106 Safari/537.36
	Accept    image/webp,image/*,*/*;q=0.8
	Referer    http://www.imooc.com/
	Accept-Encoding    gzip, deflate, sdch
	Accept-Language    zh-CN,zh;q=0.8

####请求方法
* GET   从服务器获取资源
* POST  更新服务器资源
* PUT   上传资源
* DELETE 删除服务器上的资源
* HEAD   类似于get请求，只不过返回的响应中没有具体的内容，用于响应头
* TRACE  追踪资源网络上的路径
* OPTIONS 查看服务器支持哪些方法

#####post和get的区别
1. get请求把请求参数放到url中，post放到请求体中，所以post数据相对安全
2. 参数在get中长度有限制（浏览器的限制输入框不能输入太长的url），post中没有



###响应部分
响应部分 = 状态行 + 响应头 + 响应体
![](https://upload-images.jianshu.io/upload_images/2964446-1c4cab46f270d8ee.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

状态行 = 版本 状态码 状态说明

	100~101  信息提示
	200~206  成功
	300~305  重定向
	400~415  客户端错误
	500~505  服务器错误










