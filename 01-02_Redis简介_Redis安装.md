## 1.2 Redis安装

第一步：redis-3.2.9.tar.gz传到Linux服务器  

第二步：解压redis-3.2.9.tar.gz

    tar zxvf redis-3.2.9.tar.gz
    make
    make install PREFIX=/usr/local/redis

第三步：拷贝redis.conf配置文件

    cp redis.conf /usr/local/redis/

第四步：默认端口是6379
