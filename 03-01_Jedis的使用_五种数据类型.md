# 3 Jedis的使用

## 3.1 五种数据类型

* 字符串
* 散列
* 列表
* 集合
* 有序集合

### 3.1.1 字符串数据类型

	set name value1
	get name
	set k1 10
	incr k1
	decr k1
	del k1

### 3.1.2 散列数据类型

存储的是键值对(key-value)

    hset h1 key1 value1
	hset h1 key2 value2
	hget h1 key1
	hget h1 key2

### 3.1.3 列表数据类型

	lpush listkey redis
	lpush lisetkey mongodb
	lpush lisetkey mysql
	lindex listkey 2
	lrange listkey 0 2

### 3.1.4 集合数据类型

Redis的set是string类型的无序集合,不能重复。

	sadd setkey redis
	sadd setkey mongodb
	sadd setkey mysql
	smembers setkey

### 3.1.5 有序集合类型

	zadd sortkey 1 redis
	zadd sortkey 2 mongodb
	zadd sortkey 3 mysql
	zrange sortkey 0 3 withscrores


