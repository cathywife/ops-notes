###SVN����
	svn -c "/usr/local/svn/bin/svnserve -d -r /usr/local/svn/data"
	svn co svn://192.168.5.211/dj/StntsCms/trunk/v2 /webser/www/minisite --username='yangwei' --password='0220ygwi'
	tar cvfz changes.tar.gz  `svn diff -rM:N --summarize . | grep . | awk '{print $2}' | grep -E -v '^\.$'`



###������֧
	svn copy svn://server/path/to/trunk svn://server/path/to/branch/newBranch -m "Cut branch: newBranch"

###�Զ�����
	#!/bin/sh
	SVN=/webser/svn/bin/svn
	WEB=/webser/www/flow
	export LANG="zh_CN.GBK"
	$SVN update $WEB --username='hlk' --password='hengleike'

###svn�ϲ�
һ�����õ�����Ӧ����svn diff-and-apply�����Ƿ����������¼������������汾�����Ƚϣ�Ȼ������Ӧ�õ����ؿ�����

��������������������

* ��ʼ�İ汾��(ͨ�������Ƚϵ����)
* ���յİ汾��(ͨ�������Ƚϵ��ұ�)
* һ����������Ĺ�������(ͨ�������ϲ���Ŀ��)

һ������������ָ���Ժ�����Ŀ¼����Ҫ���Ƚϣ��ȽϽ��������Ϊ�����޸�Ӧ�õ�Ŀ�깤������������������󣬽��ͬ���ֹ��޸Ļ�����ʹ��svn add��svn deleteû��ʲô���������ϲ��������������ύ�������ϲ���������ʹ��svn revert�ָ��޸ġ�

svn merge���﷨����ǳ�����ָ��������Ҫ�Ĳ�����������һЩ���ӣ�

	$svn merge http://svn.example.com/repos/branch1@150 \
		http://svn.example.com/repos/branch2@212 \
		my-working-copy
	$svn merge -r 100:200 http://svn.example.com/repos/trunk my-working-copy
	$svn merge -r 100:200 http://svn.example.com/repos/trunk

��һ���﷨ʹ��URL@REV����ʽֱ���г������в������ڶ����﷨����������Ϊ�Ƚ�ͬһ��URL�Ĳ�ͬ�汾�ļ���д�������һ���﷨��ʾ���������ǿ�ѡ�ģ����ʡ�ԣ�Ĭ���ǵ�ǰĿ¼��

--dry-run Ԥ���ϲ�


###�ο�����
[��֧��ϲ�](https://i18n-zh.googlecode.com/svn/www/svnbook-1.4/svn.branchmerge.copychanges.html)
