#Hadoop 설치

###Java 설치
````
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java7-installer
````

###SSH 설정
하둡은 SSH 프로토콜을 이용해 하둡 클러스터 간의 내부통신을 수행한다.
````
apt-get install openssh-server
````

- SSH설치가 완료되면 'netstat ntl'을 통해 SSH프로토콜이 제대로 설치되었는지를 확인한다.
- Active Internet connections목록에서 Local Address 열과 State를 통해 SSH 통신 상태를 확인한다.
- Local Address:0.0.0.0:22, ::: 22 State:LISTEN

````
ssh-keygen-t rsa
````
한쌍의 RSA 공개키를 생성한다.

###Hadoop 다운로드
````
cp R /home/hadoop/Downloads/hadoop-1.2.1   /usr/local
````
usr/local 폴더로 복사한다.


````
cd usr/local
````
hadoop-1.2.1 폴더가 /usr/local 디렉토리에 복사가 제대로 됐는지 확인


####Hadoop 환경파일 설정
하둡 설치 과정에서 환경 설정을 위한 중요 파일들이 있다.
의사분산 모드(Pseudo-distributed mode)에서는 4개의 파일만 수정한다.
````
core-site.xml
hdfs-site.xml
mapred-site.xml
hadoop-env.sh
````

````
./bin/hadoop namenode -format
````
하둡 파일 시스템(HDFS) 포맷팅

````
./bin/start-all.sh
````
데몬 프로세스 실행

````
NameNode
SecondaryNameNode
TaskTracker
DataNode
JobTracker
````
자바의 jsp 명령어를 사용하여 데몬이 동작하고 있는지 확인
