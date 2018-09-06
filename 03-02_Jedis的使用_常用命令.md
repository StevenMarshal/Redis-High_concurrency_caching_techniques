## 3.2 常用命令

客户端连接:

    redis-cli -h xx.xx.xx -p xx

默认有16个数据库0-15

    select x

当前数据库的key数量：

    dbsize

清除当前库的所有key:

    flushdb

清除所有库的所有key:

    flushall

列出所有的key

    keys *  

保存:

    save
