

# 1. Centos 7.2

1. 设置允许连接网络： vi /etc/sysconfig/network-scripts/ifcfg-enp0s3  

2. ONBOOT=yes

3. service network restart

4. 安装net-tools：

   yum install net-tools

5. 装wget

   yum install wget

6. yum install vim

7. 备份默认源

   mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

8. 进入到/etc/yum.repos.d/目录：
   cd /etc/yum.repos.d/

9. 添加源
   wget http://mirrors.163.com/.help/CentOS7-Base-163.repo

10. 运行一下命令生成缓存:
   yum clean all
   yum makecache

```shell
#改时间
ntpdate 218.186.3.36
timedatectl set-timezone Asia/Shanghai

0 */2 * * * /usr/sbin/ntpdate -u ntp.api.bz > /dev/null 2>&1; /sbin/hwclock -w
#改时区
```

# 2. 指令

```shell

#添加一个user的新账号
groupadd user
tail /etc/group
useradd -d /home/user -g 1001 -u 1001 -m -s /bin/bash user
passwd user


#更改文件所属用户组
chown -R user /home/software
chgrp -R user /home/software


#查看端口
netstat命令各个参数说明如下：
　　-t : 指明显示TCP端口
　　-u : 指明显示UDP端口
　　-l : 仅显示监听套接字(所谓套接字就是使应用程序能够读写与收发通讯协议(protocol)与资料的程序)
　　-p : 显示进程标识符和程序名称，每一个套接字/端口都属于一个程序。
　　-n : 不进行DNS轮询，显示IP(可以加速操作)
即可显示当前服务器上所有端口及进程服务，于grep结合可查看某个具体端口及服务情况··
netstat -ntlp   //查看当前所有tcp端口·
netstat -ntulp |grep 80   //查看所有80端口使用情况·
netstat -an | grep 3306   //查看所有3306端口使用情况·
查看一台服务器上面哪些服务及端口
netstat  -lanp
#查看一个服务有几个端口。比如要查看mysqld
ps -ef |grep mysqld
#查看java
jps
查看某一端口的连接数量,比如3306端口
netstat -pnt |grep :3306 |wc
#查看某一端口的连接客户端IP 比如3306端口
netstat -anp |grep 3306
netstat -an 查看网络端口 


#tomcat
wget http://mirror.bit.edu.cn/apache/tomcat/tomcat-9/v9.0.20/bin/apache-tomcat-9.0.20.tar.gz
tar -zxvf apache-tomcat-9.0.20.tar.gz

sh /home/software/apache-tomcat-9.0.20/bin/startup.sh
sh /home/software/apache-tomcat-9.0.20/bin/shutdown.sh
ps -ef | grep java

kill -9 1858
lsof -i:8080
#netstat -p | grep 8080
vi /home/software/apache-tomcat-9.0.20/conf/server.xml
tail -100 /home/software/apache-tomcat-9.0.20/logs/catalina.out


mvn spring-boot:run
mvn install:install-file -Dfile=/home/api-client-1.0.0.jar -DgroupId=org.huawei -DartifactId=api-jar -Dversion=1.0 -Dpackaging=jar
mvn install:install-file -Dfile=E:\workspaces\OceanConnect_Java_SDK_Demo\lib\api-client-1.0.0.jar -DgroupId=org.huawei -DartifactId=api-jar -Dversion=1.0 -Dpackaging=jar




#jdk
wget https://download.oracle.com/otn/java/jdk/8u211-b12/478a62b7d4e34b78b671c754eaaf38ab/jdk-8u211-linux-x64.tar.gz?AuthParam=1558042901_134f6c4f31ff682567fbd19dbbf85650
mv jdk-8u211-linux-x64.tar.gz?AuthParam=1558042901_134f6c4f31ff682567fbd19dbbf85650  jdk1.8.tar.gz
tar -zxvf jdk1.8.tar.gz
vi /etc/profile
#添加
export JAVA_HOME=/home/software/jdk1.8.0_211
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JAVA_HOME/jre/lib/rt.jar
export PATH=$JAVA_HOME/bin:$PATH

wget https://repo.mysql.com//mysql80-community-release-el7-3.noarch.rpm
rpm -ivh mysql80-community-release-el7-3.noarch.rpm
yum install mysql mysql-server -y


#查看文件大小
du -h ftp
#查看磁盘
df -u
#测速
pip install speedtest-cli
运行命令：
speedtest-cli --bytes


lsof -i :port，使用lsof -i :port就能看见所指定端口运行的程序，同时还有当前连接。 

nmap 端口扫描
netstat -nupl  (UDP类型的端口)
netstat -ntpl  (TCP类型的端口)
netstat -anp 显示系统端口使用情况
常用组合：
netstat -lntup 
说明： l:listening   n:num   t:tcp  u:udp  p:process 


#安装lrzsz 
#apt-get install lrzsz
yum -y install lrzsz 
#上传文件，执行命令rz，会跳出文件选择窗口，选择好文件，点击确认即可。
rz
#下载文件，执行命令sz
sz


```


# 3. mysql安装
1. 移除mariadb数据库
      yum remove mariadb-libs.x86_64

2. cd /usr/local/

3. wget https://dev.mysql.com/get/mysql57-community-release-e17-11.noarch.rpm

4. yum localinstall mysql57-community-release-el7-11.noarch.rpm

5. yum install mysql-community-server

6. service muysqld start

7. 查密码cat /var/log/mysqld.log |grep password

8. mysql -uroot -p

9. 输入密码

10. 修改全局参数：
        set global validate_password_policy=0;
        set global validate_password_length=1;

11. 设密码
    SET PASSWORD = PASSWORD('123456');

12. exit

13. iptables -l INPUT 1 -p tcp --dport 3306 -j ACCEPT

14. mysql -uroot -p123456

15. 依次执行如下命令：(添加远程连接)

    use mysql;

    update user set host = '%' where user ='root';

    flush privileges;
    
16. 改字符集

17. ```
    show VARIABLES like 'character%';
    修改my.cnf配置文件（mysql配置文件）
    character_set_server = utf8 #设置字符集
    
    ```

##使用
1.service mysqld start
2.mysql -uroot -p123456
3.show databases;
4.use [数据库名]
5.show tables;
6.exit

#jdk
1.cd /usr/local
2.mkdir java
   cd /usr/local/java   
3.yum install tar
   tar -zxvf jdk1.8.tar.gz
4.mv jdk1.8 jdk
   vim /etc/profile

```shell
JAVA_HOME=/usr/local/java/jdk
PATH=$JAVA_HOME/bin:$PATH
CLASSPATH=$JAVA_HOME/jre/lib/ext:$JAVA_HOME/lib/tools.jar
export PATH JAVA_HOME CLASSPATH
source /etc/profile
```





# 4. kafka
1. wget http://apache.fayea.com/kafka/1.1.0/kafka_2.12-1.1.0.tgz
   /usr/local 路径下
2. 解压tar -zxvf kafka_2.12-1.1.0.tgz
   mv kafka_2.12-1.1.0.tgz-1.1.0 kafka
3. 编辑server.properties
vim /usr/local/kafka/config/server.properties

​       添加
​       listeners=PLAINTEXT://172.16.40.173:9092

4. 对外开放 9092端口
  iptables -l INPUT 1 -p tcp --dport 9092 -j ACCEPT

## 4.1. 使用


1. 启动Zookeeper服务器
   cd /usr/local/kafka
   bin/zookeeper-server-start.sh config/zookeeper.properties

2. 启动kafka服务
    cd /usr/local/kafka
    bin/kafka-server-start.sh config/server.properties &
    
    
    
3. 建"test" Topic 只有一个分区和一个备份
  
```shell
cd /usr/local/kafka
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
```

选项说明：

--topic 定义topic名

--replication-factor  定义副本数

--partitions  定义分区数

kafka0.9以后

```shell
#删除topic
bin/kafka-topics.sh --zookeeper hadoop102:2181 --delete --topic test
#需要server.properties中设置delete.topic.enable=true否则只是标记删除或者直接重启。
#生产者
bin/kafka-console-producer.sh --broker-list 172.16.40.173:9092 --topic test
#消费者
bin/kafka-console-consumer.sh --bootstrap-server 172.16.40.173:9092 --topic test --from-beginning
```



kafka之前

```shell

#发送消息
bin/kafka-console-producer.sh 
--broker-list hadoop102:9092 --topic first
>hello world
>atguigu  atguigu
#消费消息
bin/kafka-console-consumer.sh --zookeeper hadoop102:2181 --from-beginning --topic test
--from-beginning：会把first主题中以往所有的数据都读取出来。根据业务场景选择是否增加该配置。

#查看某个Topic的详情
[atguigu@hadoop102 kafka]$ bin/kafka-topics.sh --zookeeper hadoop102:2181 --describe --topic first

#通过以下命令查看已创建的topic信息
bin/kafka-topics.sh --list --zookeeper localhost:2181 test
#发送消息
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
#消费消息
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning

```

~~bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning~~

```shell
startvm "D:\VM\ubuntu\Ubuntu 16.04.6.vmx"
D:\virtualbox\VBManage.exe startvm centos
D:\virtualbox\VBManage.exe controlvm centos pause(savestate)
D:\virtualbox\VBManage.exe controlvm centos resume
schtasks /create /tn "shutdown" /tr "D:\timetask\shutdown.bat" /sc DAILY /st 16:59
schtasks /create /tn "vmstart" /tr "D:\timetask\vmstart.bat" /sc DAILY /st 08:33
schtasks /create /tn "vmsuspend" /tr "D:\timetask\vmsuspend.bat" /sc DAILY /st 16:58
```

