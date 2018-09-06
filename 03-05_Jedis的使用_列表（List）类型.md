## 3.5 列表List

### 3.5.1 可以有相同元素

创建list  :

	jedis.lpush("list1", "v1");
	jedis.lpush("list1", "v2");
	jedis.lpush("list1", "v3");

取数

	List list=jedis.lrange("list1", 0, 2);
	Iterator iterator=list.iterator();
	while(iterator.hasNext()){
		System.out.println(iterator.next());
	}

    jedis.lrange("list1", 0, -1);//-1表示所有

计算列表长度:

	jedis.llen("list1");

删除:

	jedis.del("list1");

移除元素:

	jedis.lrem("list1", 3, "v3");

根据参数 COUNT 的值，移除列表中与参数 VALUE 相等的元素。

COUNT 的值可以是以下几种：
* count > 0 : 从表头开始向表尾搜索，移除与 VALUE 相等的元素，数量为 COUNT 。
* count < 0 : 从表尾开始向表头搜索，移除与 VALUE 相等的元素，数量为 COUNT 的绝对值。
* count = 0 : 移除表中所有与 VALUE 相等的值。

反方向:

	jedis.rpush("list1", "v1");
	jedis.rpush("list1", "v2");
	jedis.rpush("list1", "v3");
	        
	List list=jedis.lrange("list1", 0, -1);
	Iterator iterator=list.iterator();
	while(iterator.hasNext()){
		System.out.println(iterator.next());
	}
