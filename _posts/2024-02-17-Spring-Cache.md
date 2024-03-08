---
title: Spring-Cache
date: 2024-02-17 10:34:00 +0800
categories: [随笔]
tags: [学习]
pin: true
author: superWang
toc: true
comments: true
math: false
mermaid: true
typora-root-url: ../../littleWang1.github.io
---

# 1.Spring Cache介绍

![image-20240217085339893](/assets/blog_res/2024-02-17-Spring-Cache.assets/image-20240217085339893.png)

# 2.常用注解

![image-20240217085400512](/assets/blog_res/2024-02-17-Spring-Cache.assets/image-20240217085400512.png)

静态设置key

`@CachePut(cacheNames = "userCache" key = "abc")//如果使用Sspring Cache缓存数据，key的生成: userCache : : abc`



动态设置key

UserController中插入

写法一：

`CachePut( cacheMames = "userCache" key = “#user.id")//如果使用Spring Cache缓存数据，key的生成:userCache..abc`

`public User save(@RequestBody User` user){

写法二：

`/@CachePut(cacheNames = "usercache" ,key = " #result.id")//对象导航`

写法三：

` @CachePut( cacheNames = "userCache" , key = "#po.id")`

写法四：

`(@CachePut( cacheNames = "userCache" , key = "#a0.id")`

写法五：

`@CachePut(cacheNames = "userCache" ,key = " #root.args[0].id")`



Mapper中代码

插入

`@Insert("insert into user(name,age) values ( #{name}, {age})")`

`@options(useGeneratedKeys = true,keyProperty = "id")`
`void insert(User user);`



查找

`@GetMapping v
@Cacheable(cacheNames = "userCache" , key = "#id") / / key的生成: userCache ::10`

`public User getById(Long id){
User user = userMapper.getById(id);"
return user};`



删除

`@DeleteMappingv`
`@CacheEvict(cacheNames = "userCache" ,key = "#id") // key的生成:userCache::1d]`

`public void deleteById(Long id){`
`userMapper.deleteById( id);`
`}`

删除全部

`@DeleteMapping("/ delAll")
@CacheEvict(cacheNames = "userCache",allEntries = true)`

`public void deleteAll(){`
`userMapper.deleteAl1();`
`}`
