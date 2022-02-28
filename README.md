# Docker PHP 开发环境



集成了PHP、Nginx、MySQL、Redis、Rabbitmq等快速构建一个Docker的PHP开发环境，通过.env可以自定义版本选择，移除了node，因为node在docker中开发会产生一些问题，建议node在宿主机下开发更方便。




## 目录结构


```pgp
├── code                      项目代码目录
├── services                  Docker服务
│   ├── mysql                 MySQL服务
│   │   ├── conf              MySQL配置存放
│   │   └── Dockerfile        MySQL构建文件
│   │
│   ├── nginx                 Nginx服务
│   │   ├── conf              Nginx配置存放
│   │   └── Dockerfile        Nginx构建文件
│   │
│   ├── php                   PHP服务
│   │   ├── conf              PHP配置存放
│   │   └── Dockerfile        PHP构建文件
│   │
│   ├── rabbitmq              Rabbitmq服务
│   │   ├── conf              Rabbitmq配置存放
│   │   └── Dockerfile        Rabbitmq构建文件
│   │ 
│   ├── redis                 Redis服务
│   │   ├── conf              Redis配置存放
│   │   └── Dockerfile        Redis构建文件
```



## 快速开始

```shell
$ git clone https://github.com/uutuwen/docker-php.git
$ cd docker-php
$ cp .env.example .env
$ docker-compose up -d --build
```

根据自己需求修改.env环境配置之后再构建即可。



## 快捷指令

```shell
$ cd docker-php
$ source ./.bashrc
```



## 补充说明

默认不会开启php-fpm，如果需要开启php-fpm只需进入容器Bash后执行'php-fpm'即可，如需停止php-fpm，可以通过 **kill -INT cat /var/log/php7/php-fpm.pid** 注意'php7'对应你的PHP_VERSION_TAG。

