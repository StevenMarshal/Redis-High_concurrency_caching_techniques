## 4.2 Redis集群安装

安装ruby

	yum install ruby
	yum install rubygems

下载redis.gem

	https://rubygems.org/gems/redis/
	gem install redis-3.3.3.gem

redis集群管理工具

	src/redis-trib.rb

修改redis.conf配置文件

	port 7001
	cluster-enabled yes

说明：
* redis集群至少需要3个主节点，每个主节点有一个从节点总共6个节点
* replicas指定为1表示每个主节点有一个从节点

启动6个redis服务

	/etc/security/limits.conf
	ulimit -a
	* soft nofile 65535
	* hard nofile 65535

编写启动脚本:

	cat start.sh 
	cd redis01
	bin/redis-server redis.conf
	cd ../redis02
	bin/redis-server redis.conf
	cd ../redis03
	bin/redis-server redis.conf
	cd ../redis04
	bin/redis-server redis.conf
	cd ../redis05
	bin/redis-server redis.conf
	cd ../redis06
	bin/redis-server redis.conf

每个redis文件夹里面都产生一个nodes.conf文件

	./redis-trib.rb create --replicas 1 192.168.230.100:6381 192.168.230.100:6382 192.168.230.100:6383 192.168.230.100:6384 192.168.230.100:6385 192.168.230.100:6386

一共16384个slot

测试集群:

	./redis-cli -h 172.16.41.151 -c -p 7001
	-c  集群
