# Redis 简介

## 历史

`Redis` 是完全开源的，遵守 `BSD` 协议，是一个高性能的 `key-value` 数据库。

`2008` 年，意大利的一家创业公司 `Merzia` 推出了一款基于 `MySQL` 的网站实时统计系统 `LLOOGG` 。

没过多久，创始人 `Salvatore Sanfilippo` 对 `MySQL` 的性能大失所望，于是他决定自己写一个数据库。

`2009` 年，`Salvatore` 老哥完成了数据库的编写，这就是 `Redis` 。

## 优势

**速度快**

- 读可达 `11` 万次/秒，写可达 `8` 万次/秒。
- 数据存储在内存中。
- 使用`C`语言编写。
- 采用单线程模型。

### 持久化

`Redis`所有数据保持在内存中，对数据的更新将异步地保存到磁盘上。

### 多种数据结构

- `String`
- `Hash Tables`
- `Linked Lists`
- `Sets`
- `Sorted Set`

### 支持多种客户端语言

- `Java`
- `PHP`
- `Python`
- `Ruby`
- `Lua`
- `NodeJS`

### 功能丰富

- 发布订阅
- `Lua`脚本
- 事务
- `Pipeline`

### 简单

- 不依赖外部库
- 单线程模型

### 主从复制

`Redis`支持主从复制。

### 高可用分布式

`Redis-Sentinel(v2.8)`支持高可用。

`Redis-Cluster(v3.0)`支持分布式。