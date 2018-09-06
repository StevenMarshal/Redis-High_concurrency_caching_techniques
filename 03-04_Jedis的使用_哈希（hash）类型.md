## 3.4 哈希hash

### 3.4.1 设置和获取hash值

	jedis.hset("hash1", "h1", "v1");
	jedis.hset("hash1", "h2", "v2");
	jedis.hset("hash1", "h3", "v3");
	System.out.println(jedis.hget("hash1", "h1"));
	System.out.println(jedis.hget("hash1", "h2"));
	System.out.println(jedis.hget("hash1", "h3"));

### 3.4.2 获取所有field-value:

	Set set=jedis.hkeys("hash1");
	Iterator iterator=set.iterator();
	while(iterator.hasNext()){
	    String str1=(String) iterator.next();
	    String str2=jedis.hget("hash1", str1);
	    System.out.println(str1+":"+str2);
	}

或者:

	HashMap<String, String> hMap=(HashMap<String, String>) jedis.hgetAll("hash1");
	Iterator iterator= hMap.entrySet().iterator();
	while(iterator.hasNext()){
	    Entry entry= (Entry) iterator.next();
	    String str1= (String) entry.getKey();
	    String str2= (String) entry.getValue();
	    System.out.println(str1+":"+str2); 	  
	}

### 3.4.3 获取多个field的值:

	List<String> list=jedis.hmget("hash1", "h1","h2","h3");
	Iterator iterator=list.iterator();
	while(iterator.hasNext()){
	    System.out.println(iterator.next());
	}
