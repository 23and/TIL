#Hadoop ��ġ

###Java ��ġ
````
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java7-installer
````

###SSH ����
�ϵ��� SSH ���������� �̿��� �ϵ� Ŭ������ ���� ��������� �����Ѵ�.
````
apt-get install openssh-server
````

SSH��ġ�� �Ϸ�Ǹ� 'netstat ?ntl'�� ���� SSH���������� ����� ��ġ�Ǿ������� Ȯ���Ѵ�.
Active Internet connections��Ͽ��� Local Address ���� State�� ���� SSH ��� ���¸� Ȯ���Ѵ�.
Local Address:0.0.0.0:22, ::: 22
State:LISTEN

````
ssh-keygen-t rsa
````
�ѽ��� RSA ����Ű�� �����Ѵ�.

###Hadoop �ٿ�ε�
````
cp ?R /home/hadoop/Downloads/hadoop-1.2.1   /usr/local
````
usr/local ������ �����Ѵ�.


````
cd usr/local
````
hadoop-1.2.1 ������ /usr/local ���丮�� ���簡 ����� �ƴ��� Ȯ��


####Hadoop ȯ������ ����
�ϵ� ��ġ �������� ȯ�� ������ ���� �߿� ���ϵ��� �ִ�.
�ǻ�л� ���(Pseudo-distributed mode)������ 4���� ���ϸ� �����Ѵ�.
````
core-site.xml
hdfs-site.xml
mapred-site.xml
hadoop-env.sh
````

````
./bin/hadoop namenode -format
````
�ϵ� ���� �ý���(HDFS) ������

````
./bin/start-all.sh
````
���� ���μ��� ����

````
NameNode
SecondaryNameNode
TaskTracker
DataNode
JobTracker
````
�ڹ��� jsp ��ɾ ����Ͽ� ������ �����ϰ� �ִ��� Ȯ��