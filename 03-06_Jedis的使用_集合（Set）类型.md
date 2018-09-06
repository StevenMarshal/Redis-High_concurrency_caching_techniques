## 3.6 集合Set

不能出现相同元素

创建set并写入数据:

	jedis.sadd("set1", "v1");
	jedis.sadd("set1", "v2");
	jedis.sadd("set1", "v3");

取数:

	Set set= jedis.smembers("set1");
	Iterator iterator=set.iterator();
	while(iterator.hasNext()){
	      System.out.println(iterator.next());
	}

计算set元素数量:

    jedis.scard("set1");

移除某个元素:

    jedis.srem("set1", "v1");
