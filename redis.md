###�������
[php��չ](phpredis https://github.com/nicolasff/phpredis)
[redis����](http://redis.io/download)

###��װ
��װ��ѹ�����ļ�mv�ŵ�Ҫ��װ��Ŀ¼ make ����

	wget http://download.redis.io/releases/redis-2.8.5.tar.gz
	tar zxf /root/redis-2.8.5.tar.gz
	mv redis-2.8.5 /webser/redis;
	cd /webser/redis
	make -j 16

###����
./src/redis-server [/path/to/redis.conf]

###�־û�����
����save �����⣬��redis shutdown���ӻ�����������ٷ�����
rdb��ʽ��ע�����ܣ��ڿ���ʱ��������ֻ��Ҫforkһ���ӽ��̣����̵�IO�Ľ����ӽ��̼��ɡ�
aof��ע�����ݵ������ԣ�������appendonly yes����������aof�ļ��лָ����ݣ�������rdb
runtime�޸�appendonly yes�󣬿���aofǰ�������ݽ��Զ�rewrite��aof�ļ���


###�Ż�
1. Add vm.overcommit_memory = 1 to /etc/sysctl.conf and then reboot or run the command sysctl vm.overcommit_memory=1 for this to take effect immediately.
2. setup some swap
3. ����д�ܼ��Ļ�����Ӧ���ڴ�����ΪԤ�Ƶ�2��
4. ���Ӹ���ʱ����ʹ�ǹر��˿��գ�Ҳ�����
5. If you are deploying using a virtual machine that uses the Xen hypervisor you may experience slow fork() times.
6. Use daemonize no when run under daemontools


###ƽ���޸����ü�����
[modify options runtime](http://redis.io/commands/config-set)
[upgrade](http://redis.io/topics/admin upgrade), ��Ȼ������ƽ������
* ��װ�°汾newredis,������Ϊ�ϰ汾ʵ���Ĵӷ�����
* ͬ����ɺ󣬹ر�ԭredis�����Ķ˿������°�redis

###��Ⱥָ��
* down-after-milliseconds �೤ʱ��û��Ӧ��down
* can-failover �Ƿ�failover
* parallel-syncs failover��һ�������ü���slave��master��