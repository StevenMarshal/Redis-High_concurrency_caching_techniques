## 5.1 使用Java操作Redis集群

	HashSet<HostAndPort> nodes=new HashSet<HostAndPort>();	
	nodes.add(new HostAndPort("192.168.230.100", 6381));
	nodes.add(new HostAndPort("192.168.230.100", 6382));
	nodes.add(new HostAndPort("192.168.230.100", 6383));
	nodes.add(new HostAndPort("192.168.230.100", 6384));
	nodes.add(new HostAndPort("192.168.230.100", 6385));
	nodes.add(new HostAndPort("192.168.230.100", 6386));
	JedisCluster jCluster=new JedisCluster(nodes);
	jCluster.set("testj", "v1");
	System.out.println(jCluster.get("testj"));
	try {
		jCluster.close();
	} catch (IOException e) {
		e.printStackTrace();
	}
