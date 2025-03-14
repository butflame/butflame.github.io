---
layout: post
category: tech
title:  "Redisee 序"
tags: golang redis
excerpt: 一个go语言实现的redis内存使用分析工具
---

### 我想要用golang做一个redis内存使用情况的分析工具。
这个想法来源于有一个周五的晚上11点，线上缓存用的redis内存满了(2G)，本来我都陪儿子睡下了，磊哥哥一个电话给我摇起来了。

当时是我当天有上线，有用到缓存，但是预计的数据量只有几百k而已。虽然我很快就响应了，但是对内存为什么会满还是一头雾水。
坐在电脑前先是看了下监控，发现这个redis日常高峰期就到90+%了，所以第一眼就大概确认了跟我当天的上线没什么关系。
当时想着来都来了，查查看吧，于是开始想着怎么看全量key的内存占用情况。

首先就发现了阿里云提供的分析工具:

![analysis_tool](/assets/images/redisee/analysis_tool.png)

但是没有权限，于是当场开始用python手撸。当时的思路是用scan命令遍历所有的key，按「:,_-」等分隔符将key分割后，聚合计算内存使用量。
当时很快就写出来了，不过效率非常慢，而且发现了redis版本不能用memory usage命令，所以直到缓存自然降下来也没结果（当时已经快12点了）。
由于淘汰策略设置的是LRU，所以即使啥也没干也没什么影响。不过这次无疾而终还是让我有点不爽。

那就自己写一个咯，而至于选择golang的原因，一方面想重新把golang捡起来，另一方面想借助一下golang并发上的优势。
至于这个分析工具要做的事情，就准备参照阿里云的分析结果了，指标包括：
- 总内存，已使用内存
- key数量
- 不同类型的key数量分布
- 不同类型的key内存占用分布
- 所有key的过期时间分布
- Top500 BigKey
- Top500 Key前缀(按内存)
- Top500 Key前缀(按key数量)

> 磨叽的时候在github上找到了这个同类型的玩意儿，已经700+star了，搞不好咱也能整个小火一把的repo呢？
> 
> [redis-memory-analyzer](https://github.com/gamenet/redis-memory-analyzer)
