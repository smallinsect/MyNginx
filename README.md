# MyNginx

# Linux环境

教程网址

```
https://www.runoob.com/linux/nginx-install-setup.html
```

安装编译工具及库文件

```
yum -y install make zlib zlib-devel gcc-c++ libtool  openssl openssl-devel
```

首先要安装 PCRE

PCRE 作用是让 Nginx 支持 Rewrite 功能。

1、下载 PCRE 安装包，下载地址： http://downloads.sourceforge.net/project/pcre/pcre/8.35/pcre-8.35.tar.gz

```
[root@bogon src]# cd /usr/local/src/
[root@bogon src]# wget http://downloads.sourceforge.net/project/pcre/pcre/8.35/pcre-8.35.tar.gz
```

2、解压安装包

```
[root@bogon src]# tar zxvf pcre-8.35.tar.gz
```

3、进入安装包目录

```
[root@bogon src]# cd pcre-8.35
```

4、编译安装 

```
[root@bogon pcre-8.35]# ./configure
[root@bogon pcre-8.35]# make && make install
```

5、查看pcre版本

```
[root@bogon pcre-8.35]# pcre-config --version
```

### 安装 Nginx

1、下载 Nginx，下载地址：http://nginx.org/download/nginx-1.16.1.tar.gz

```
[root@bogon src]# cd /usr/local/src/
[root@bogon src]# wget http://nginx.org/download/nginx-1.16.1.tar.gz
```

2、解压安装包

```
[root@bogon src]# tar zxvf nginx-1.16.1.tar.gz
```

3、进入安装包目录

```
[root@bogon src]# cd nginx-1.16.1
```

4、编译安装

```
[root@bogon nginx-1.6.2]# ./configure --prefix=/usr/local/webserver/nginx --with-http_stub_status_module --with-http_ssl_module --with-pcre=/usr/local/src/pcre-8.35
[root@bogon nginx-1.6.2]# make
[root@bogon nginx-1.6.2]# make install
```

5、查看nginx版本

```
[root@bogon nginx-1.6.2]# /usr/local/webserver/nginx/sbin/nginx -v
```

6、配置文件

```
cat /usr/local/webserver/nginx/conf/nginx.conf
验证配置
/usr/local/webserver/nginx/sbin/nginx -t
```































