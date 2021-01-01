# Redis 持久化

`Redis` 所有数据保持在内存中，对数据的更新将异步地保存到磁盘上。

快照：`Redis RDB`

写日志：`Redis AOF`

## RDB

### 快照

如存在老的 `RDB` 文件，新文件会进行替换。

![RDB创建](assets/rdb-create.png)

![RDB恢复](assets/rdb-recovery.png)

### 触发快照

![save](assets/rdb-save.png)

![bgsave](assets/rdb-bgsave.png)

| 命令 | save | bgsave |
| --- | --- | --- |
| `IO` 类型 | 同步 | 异步 |
| 优点 | 不会消耗额外内存 | 不阻塞客户端命令 |
| 缺点 | 阻塞客户端命令 | 需要 `fork` ，消耗内存 |

## AOF

### 什么是AOF

![AOF运行原理-创建](assets/5-5.png)

![AOF运行原理-恢复](assets/5-6.png)

### AOF的三种策略

![always](assets/5-7.png)

![everysec](assets/5-8.png)

![no](assets/5-9.png)

| 命令 | always | everysec | no |
| --- | --- | --- | --- |
| 优点 | 不丢失数据 | 每秒一次fsync | 不用管 |
| 缺点 | IO开销大，一般的Sata盘只有几百TPS | 丢1秒数据 | 不可控 |

### AOF重写

![AOF重写](assets/5-10.png)

- 减少磁盘占用量
- 加速恢复速度

**bgrewriteaof**

![bgrewriteaof](assets/5-11.png)

**配置**

| 配置名 | 含义 |
| --- | --- |
| auto-aof-rewrite-min-size | AOF文件重写需要的尺寸 |
| auto-aof-rewrite-percentage | AOF文件增长率 |

**统计**

| 统计名 | 含义 |
| --- | --- |
| aof_current_size | AOF当前尺寸(单位：字节) |
| aof_base_size | AOF上次启动和重写的尺寸(单位：字节) |

## RDB和AOF的抉择

| 命令 | RDB | AOF |
| --- | --- | --- |
| 启动优先级 | 低 | 高 |
| 体积 | 小 | 大 |
| 恢复速度 | 快 | 慢 |
| 数据安全性 | 丢数据 | 根据策略决定 |
| 轻重 | 重 | 轻 |

**RDB最佳策略**

- “关”掉RDB
- 集中管理
- 主从，从开

**AOF最佳策略**

- “开”：缓存和存储
- AOF重写集中管理
- everysec

**最佳策略**

- 小分片
- 缓存或者存储
- 监控(硬盘、内存、负载、网络)
- 足够的内存