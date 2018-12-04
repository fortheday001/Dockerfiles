FROM php:7.2-fpm-alpine

MAINTAINER "fortheday fortheday@126.com"

# 使用国内 apk 包源
RUN echo http://mirrors.ustc.edu.cn/alpine/v3.8/main > /etc/apk/repositories && \
    echo http://mirrors.ustc.edu.cn/alpine/v3.8/community >> /etc/apk/repositories && \
    apk update && apk upgrade

# 安装 gd、pdo_mysql 库
RUN apk add libpng-dev && docker-php-ext-install gd pdo_mysql sockets pcntl zip mysqli opcache

# 安装 git composer
RUN apk add git composer

# 更新 pecl
RUN pecl channel-update pecl.php.net

# 安装 pecl 依赖包
RUN apk add autoconf gcc g++ make

# 安装 redis 扩展
RUN echo -e "\n\n" | pecl install redis && docker-php-ext-enable redis

# 安装 yaf 扩展
RUN pecl install yaf && docker-php-ext-enable yaf

# 安装 swoole 扩展
RUN apk add openssl-dev && echo -e "yes\nyes\n\n\n\n\n" | pecl install swoole && docker-php-ext-enable swoole
