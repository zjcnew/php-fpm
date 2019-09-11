## php-fpm7.2的docker镜像包
### 介绍
基于docker官方的php镜像[https://github.com/docker-library/php](https://github.com/docker-library/php)，7.2/stretch/fpm版本，增加了如下的php扩展：
#### 静态编译，内置的扩展：
bcmath
exif
gd
gettext
intl
mysqli
pcntl
pdo_mysql
redis
shmop
soap
sockets
sysvsem
xmlrpc
zip
#### 动态编译，第三方扩展：
redis
### 安装
#### 构建镜像
两种方式选择
##### 1.从官方仓库拉取
```
docker pull zjcnew/php-fpm:7.2.22
```
##### 2.从Dockerfile文件构建

```
git clone -b master https://github.com/zjcnew/php-fpm.git
cd php-fpm
docker build --no-cache -f Dockerfile -t php-fpm:7.2.22 .
```
#### 运行容器
```
docker run -d -v /data/html:/usr/share/nginx/html --name php zjcnew/php-fpm:7.2.22
```
#### 查看加载的php扩展
```
docker exec php /bin/bash -c '/usr/local/bin/php -m'
```
