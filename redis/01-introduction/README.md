# Redis 简介

## 历史

`2008` 年，意大利的一家创业公司推出了基于 `MySQL` 的网站实时统计系统 `LLOOGG`。

后来，公司创始人 `Salvatore Sanfilippo` 发现 `MySQL` 性能太差，不足以满足网站需求，于是他决定自己写一个数据库。

`2009` 年，`Salvatore Sanfilippo` 老哥完成了数据库的编写，这就是 `Redis`。

`Redis` 是完全开源的，一个高性能的 `Key Value` 数据库。

## 优势

`Redis` 使用 `C` 语言编写，采用单线程模型；数据存储在内存中，读可达 `11` 万次/秒，写可达 `8` 万次/秒；支持持久化。

`Redis` 支持主从复制，`Redis Sentinel` 支持高可用，`Redis Cluster` 支持分布式。

`Redis` 支持 `string`、`hash`、`list`、`set`、`zset` 等多种数据结构。