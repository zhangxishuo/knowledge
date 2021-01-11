# Redis 复制

## 主从复制

单机问题：机器故障、容量瓶颈、`QPS` 瓶颈。

主从复制作用：数据副本、扩展读性能。

数据流向是单向的，`master` 到 `slave`。

![主从复制](assets/master-slave-copy.png)

![一主多从](assets/master-many-slave.png)

## 配置

![slaveof](assets/slave-of.png)

![slaveof-no-one](assets/slave-of-no-one.png)

```text
slaveof ip port
slave-read-only yes
```

## 复制

![全量复制](assets/full-copy.png)

![部分复制](assets/part-copy.png)