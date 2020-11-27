# Redis 初识

## Redis

- 开源
- 基于键值对的存储服务系统
- 多种数据结构
- 高性能、功能丰富

## Redis 的前世今生

`2008`年，意大利的一家创业公司`Merzia`推出了一款基于`MySQL`的网站实时统计系统`LLOOGG`。

没过多久，创始人`Salvatore Sanfilippo`对`MySQL`的性能大失所望，于是他决定自己写一个数据库。

`2009`年，`Salvatore Sanfilippo`完成了数据库的编写，这就是`Redis`。

## 谁在使用 Redis

- Github
- Twitter
- StackOverflow
- 阿里巴巴
- 百度
- 微博
- 美团
- 搜狐

## Redis 的特性

### 速度快

- 支持`10W OPS(Operation Per Second)`
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

## Redis 典型应用场景

- 缓存系统
- 计数器
- 消息队列系统
- 排行榜
- 社交网络
- 实时系统

## Redis 可执行文件说明

| 执行文件 | 描述 |
| --- | --- |
| redis-server | Redis服务器 |
| redis-cli | Redis命令行客户端 |
| redis-benchmark | Redis性能测试工具 |
| redis-check-aof | AOF文件修复工具 |
| redis-check-rdb | RDB文件修复工具 |
| redis-sentinel | Sentinel服务器(v2.8) |

## Redis 三种启动方式

### 最简启动

```shell
redis-server
```

### 动态参数启动

```shell
redis-server --port 7379
```

### 配置文件启动

```shell
redis-server configPath
```

## Redis 客户端连接

```shell
PS C:\Program Files\Redis> .\redis-cli.exe -h 127.0.0.1 -p 6379
127.0.0.1:6379> ping
PONG
```

## Redis 常用配置

| 配置项 | 描述 |
| --- | --- |
| daemonize | 是否是守护进程(no/yes) |
| port | Redis对外端口号 |
| logfile | Redis系统日志 |
| dir | Redis工作目录 |