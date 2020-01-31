top可以显示系统整体以及各个进程的资源占用和消耗情况. 

```
top -p procss_num   
top -u user_name
```

Web Server Software 
--
web服务器主要用来接受客户端请求，建立连接，转发响应的程序。目前主要的web服务器主要有以下：

* Apache.
* NGINX
* Microsoft IIS
* Tornado
* XAMPP
* Caddy

Install and Run Nginx 

1. Type ```apt-get install nginx``` to install nginx on Ubuntu
2. Start Nginx by ```/etc/init.d/nginx start```
3. Then open a web browser and type the address, eg: 45.32.207.39

note:   
1. You can also check if the nginx is runing by ```htop```. There should be "nginx master proccess" and "nginx worker process" in the list.  
2. Rember everytime you make changes to the Nginx configuration file, you will neet to restart Nginx by ```/etc/init.d/nginx restart```.
3. make a copy of original config file by ```cp  /etc/nginx/nginx.conf  /etc/nginx.conf.orig ```

Ref: http://tutorials.jenkov.com/nginx/index.html

WSGI
--
WSGI是一个针对python的WEB服务器网关接口协议，定义了WEB服务器如何与Python应用程序间的交互，它相当于两者之间的一个桥梁，两者只要满足WSGI协议便能相互搭配。总而言之，它可实现以下三个功能：

1. 让web服务器知道如何调用Python应用程序，并且把用户的请求告诉应用程序
2. 让python应用程序知道用户的具体请求是什么，以及如何返回结果给web服务器
3. 它统一了python不通的网络框架和web服务器之间的通信协议

uWSGI
--
一种实现了WSGI协议的web服务器，即用来接受客户端请求，并使用WSGI协议将请求转发给python网络应用服务。实际上，一个uWSGI的web服务器，再加上Django这样的web框架，就已经可以实现网站的功能了

既然有了uWSGI，为何还需要Nginx？
当访问量一旦过大，就需要分布式服务器，即需要多台web服务器来处理请求，Nginx可以实现反向代理，即代理服务器。
