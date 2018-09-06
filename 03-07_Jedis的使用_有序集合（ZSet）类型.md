## 3.7 有序集合Sorted Set

创建:

	jedis.zadd("zset1", 100, "v1");
	jedis.zadd("zset1", 200, "v2");
	jedis.zadd("zset1", 300, "v3");

如果再次执行

	jedis.zadd("zset1", 30, "v3");

则将v3的score修改为30

或者

	HashMap<String, Double> hMap=new HashMap<String, Double>();
	hMap.put("v1", 100D);
	hMap.put("v2", 200D);
	hMap.put("v3", 300D);
	jedis.zadd("zset1", hMap);

计算元素个数:

	jedis.zcard("zset1");

获取元素的分数:

	jedis.zscore("zset1", "v3");

一个元素只有一个分数

获取zset元素和值:

	Set<Tuple> set=jedis.zrangeWithScores("zset1", 0, -1);
	Iterator iterator=set.iterator();
	while(iterator.hasNext()){
		Tuple tuple=(Tuple) iterator.next();
	    System.out.println(tuple.getElement()+":"+tuple.getScore());
	}
