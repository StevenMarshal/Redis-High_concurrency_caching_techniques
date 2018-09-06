# 2 Redis启动

## 2.1 前端启动模式

通过直接运行bin/redis-server将以前端模式启动。  
前端模式启动的缺点是ssh命令窗口关闭则redis-server程序结束，不推荐使用此方法。

    bin/redis-server ./redis.conf