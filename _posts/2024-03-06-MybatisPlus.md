---
title: WebSpcket
date: 2024-03-06 10:34:00 +0800
categories: [MyBatisPlus]
tags: [学习]
pin: true
author: superWang
toc: true
comments: true
math: false
mermaid: true
typora-root-url: ../../littleWang1.github.io
---

# 1.MyBatis基础

## 1.常见注解

<img src="/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306140906069.png" alt="image-20240306140906069" style="zoom:50%;" />

## 2.mp约定

![image-20240306141000598](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306141000598.png)

## 3.自定义配置

<img src="/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306141028949.png" alt="image-20240306141028949" style="zoom:67%;" />

注意![image-20240306141157074](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306141157074.png)中有几种策略

![image-20240306141226405](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306141226405.png)

@TableField常见场景

![image-20240306141325794](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306141325794.png)

## 4.常见配置

![image-20240306143534438](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306143534438.png)

## 5.使用流程

![image-20240306144004717](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306144004717.png)

# 2.使用mp构造复杂的where条件

![image-20240306144355186](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306144355186.png)

自定义SQL

![image-20240306154020610](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306154020610.png)

<img src="/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306154244820.png" alt="image-20240306154244820" style="zoom:67%;" />

# 3.Service接口

![image-20240306161430891](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306161430891.png)

Controller接口

![image-20240306164746411](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306164746411.png)

Service接口

Iservice批量新增

![image-20240306181729508](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306181729508.png)

![image-20240306181801205](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306181801205.png)

第三种是mysql驱动去做，是mysql的jar包去做，并不是mybatis去做，让mysql重新对数据进行处理

![image-20240306182114245](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306182114245.png)

使用方法：



![image-20240306182020824](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306182020824.png)

![image-20240306182143864](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306182143864.png)

# 4.mp代码生成工具 mybatisplus



![image-20240306183412680](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306183412680.png)

![image-20240306183433431](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306183433431.png)

# 5.静态工具

 

![image-20240306200858157](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306200858157.png)

# 6.逻辑删除

<img src="/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306201309406.png" alt="image-20240306201309406" style="zoom:67%;" />

![image-20240306201639254](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306201639254.png)

缺点

![image-20240306201954730](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306201954730.png)

枚举处理器

1.加注解@EnunValue，告诉mp告诉哪个成员变量和数据库中的字段相对应

![image-20240306210220264](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306210220264.png)

2.让处理器生效

![image-20240306210435868](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306210435868.png)

利用@JsonValue确定返回值是什么类型，加在value上就是返回的数字，加在desc返回的就是正常/冻结，不加的话返回NORMAL/FROZEN

![image-20240306210852493](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306210852493.png)



# 7.Json处理器

第一步给字段上定义一个处理器，第二步开启自动的ResultMap映射

![image-20240306211935956](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306211935956.png)

# 8.插件功能

![image-20240306212415087](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306212415087.png)

## 第一步：首先要在配置类中注册MyBatisPlus的核心插件，同时添加分页功能

![image-20240306212919575](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306212919575.png)

## 第二部：就可以使用分页的API了

![image-20240306213618005](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306213618005.png)

![image-20240306213745431](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306213745431.png)

例子：

![image-20240306215143697](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306215143697.png)

![image-20240306215209073](/assets/blog_res/2024-03-06-MybatisPlus.assets/image-20240306215209073.png)
