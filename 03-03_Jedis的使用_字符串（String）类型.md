## 3.3 字符串String类型

连接jedis：  

    Jedis jedis=new Jedis("192.168.230.100", 6379);

获取key的值:

    String str=jedis.get("name");

设置key的值:

    jedis.set("key1", "value1");

删除key的值:

    jedis.del("key1");

增加key的值:

    jedis.set("num1", "10");
    long lg=jedis.incr("num1");

获取数据库中key的数量:

    jedis.dbSize()

获取所有key-value:

    Set set=jedis.keys("*");
	Iterator iterator= set.iterator();
	while(iterator.hasNext()){
	    String key=(String) iterator.next();
	    String value=jedis.get(key);
	    System.out.println(key+":"+value);
	}
