**一个个人博客项目**

使用java编写，采用mvc编程，前端页面使用html+css+js完成，没有使用jsp和框架。
数据传输使用ajax传输，数据格式是json。
实现的功能有登陆注册，写博客，查看博客，发表博客。涉及到的知识点有servlet，jdbc，
web前端，json，ajax，mysql，tomcat，filter锁，session域
功能不多但是javaWeb项目涉及到的知识点基本都有，可以作为一个javaWeb项目的练手。不过
我的前端页面写的非常简陋，主要练习的地方在于后台和js前台的逻辑，所以静态页面写的很丑。

**环境**

Tomcat版本是8.0,mysql版本是8.0，jdk环境为1.8，使用了idea编辑

mysql需要建两张表 t_user,t_article,第一张表保存了用户信息，第二张表保存每个用户
的博客，sql语句如下

**建表**

首先建立一个数据库myblog
sql语句：
CREATE DATABASE `myblog`;

t_user:

CREATE TABLE `t_user` (
  `id` int NOT NULL AUTO_INCREMENT,
  `username` varchar(20) NOT NULL,
  `password` varchar(32) NOT NULL,
  `email` varchar(200) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `username` (`username`)
) ENGINE=InnoDB AUTO_INCREMENT=24 DEFAULT CHARSET=utf8;

t_article:

CREATE TABLE `t_article` (
  `id` int NOT NULL AUTO_INCREMENT,
  `title` varchar(200) DEFAULT NULL,
  `main` text,
  `username` varchar(32) NOT NULL,
  PRIMARY KEY (`id`),
  KEY `username` (`username`),
  CONSTRAINT `t_article_ibfk_1` FOREIGN KEY (`username`) REFERENCES `t_user` (`username`)
) ENGINE=InnoDB AUTO_INCREMENT=12 DEFAULT CHARSET=utf8;



