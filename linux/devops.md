颜色`#3A4386`

```shell
netstat -an
add-apt-repository ppa:webupd8team/java
lz

```


```shell
设备名称：
BearPi

#设备ID
ae446a4e-1617-46e7-bb36-bbb4738b4ef3
#PSK码（使用DTLS协议时需要使用到该psk码，请您牢记！）
#a5338b95714cf5cd41260b5f6b0aff2c
项目名
ob_test
应用ID
i68JulxnGNrsZiJkgPg5wfrvSJMa
应用密钥
t6_ylil6j6ubkgxDBXQjAtRi160a
虚拟设备0000000000000000000000000000000000000
设备ID：8b5b8179-b817-46ff-a476-8a0216b05002
Secret：e30bdd23065ec5c19fc2
虚拟设备
ID:4fd32f3e-d16a-43c8-8bf9-581524d001cc
设备ID
0023b30c-0549-46d2-9327-4378e9a88c9d
应用服务器调用平台鉴权API时，需要将密钥作为“secret”参数的取值。
密钥
37a8b0fc0f8a76513f86
HTTPS 接入方式
49.4.92.191:8743
https://39.96.83.147:8099/v1.0.0/messageReceiver
http://114.116.6.0:8080/RESTfulWS/rest/UserInfoService/subscriber1

AppId: A_93xVRJbrZRrl5fjqP5W6CTxnMa	

AppSecret: 93ez4sYjkmfqPl3SkAPXpZ_fCo0a
    
2019/05/20/14:30:51 [INFO] (https-jsse-nio-8099-exec-3) receive(), {"deviceId":"ae446a4e-1617-46e7-bb36-bbb4738b4ef3","commandId":"5c2534b13b4343fb966ecc461100e462","result":{"resultCode":"DELIVERED","resultDetail":null}} 
2019/05/20/14:30:51 [INFO] (https-jsse-nio-8099-exec-7) receive(), {"deviceId":"ae446a4e-1617-46e7-bb36-bbb4738b4ef3","commandId":"5c2534b13b4343fb966ecc461100e462","result":{"resultCode":"SUCCESSFUL","resultDetail":{"light_state":1}}} 
2019/05/20/14:32:12 [INFO] (https-jsse-nio-8099-exec-3) receive(), {"deviceId":"ae446a4e-1617-46e7-bb36-bbb4738b4ef3","commandId":"54f18b68d5444a4097c7da67ede7e89a","result":{"resultCode":"DELIVERED","resultDetail":null}} 
2019/05/20/14:32:12 [INFO] (https-jsse-nio-8099-exec-7) receive(), {"deviceId":"ae446a4e-1617-46e7-bb36-bbb4738b4ef3","commandId":"54f18b68d5444a4097c7da67ede7e89a","result":{"resultCode":"SUCCESSFUL","resultDetail":{"light_state":0}}} 




https://iot-dev.huaweicloud.com/#/applications/i68JulxnGNrsZiJkgPg5wfrvSJMa/products/5ce3590ce4a9640d22fed829/development/codec-plugin
#管理控制台
https://iot-dev.huaweicloud.com:8843
https://iot-sp.huaweicloud.com/#/pages/device/device-explorer/device-list

https://iot-sp.huaweicloud.com/#/pages/sp-dashboard


应用对接地址:
8743/HTTPS
设备对接地址:
8883/MQTTS
8943/HTTPS
5683/COAP/UDP
5684/COAP/UDP/DTLS
```

```shell
#OpenSSL-Win64\bin\openssl.exe
genrsa -des3 -out client.key 2048
req -new -key client.key -out client.csr
x509 -req -days 365 -in client.csr -signkey client.key -out client.crt

test_iot
root
test1230.
114.116.6.0 (弹性公网) 2 Mbit/s
192.168.0.23(私有)
http://mirror.bit.edu.cn/apache/tomcat/tomcat-9/v9.0.20/bin/apache-tomcat-9.0.20.tar.gz

```

```shell
npm install -g vue-cli

```

| 工作项类型 | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| Epic       | 通常是公司重要战略举措，比如在凤凰项目中的 “凤凰商城” ，对于“无极限零部件公司”是一个与企业生存攸关的关键战略措施 |
| Feature    | 通常是对用户有价值的功能，用户可以通过使用特性满足他们的需求。比如 “凤凰商城” 中的 “门店网络查询功能”，特性通常会通过多个迭代持续交付 |
| Story      | 通常是对一个功能进行用户场景细分，并且能在一个迭代内完成，Story通常需要满足INVEST原则 |
| Task       | 通常是用户故事的细分，准备环境，准备测试用例等都可以是完成Story的细分任务 |

```shell
test["authorID"],test["number"]
 papers_num.append(item["papers_num"])
 
 
 for item in json_data['data']:    
  print(item['author_id'])
  
  
  
git clone https://codehub.devcloud.huaweicloud.com/DevOpsylcsxm00001/phoenix-storage.git

[2019-05-18 23:32:50.363] WARNING! Using --password via the CLI is insecure. Use --password-stdin.
步骤一：登陆仓库

使用容器镜像服务的第一步是获取登录Docker访问权限，并复制到节点上执行。
docker login -u cn-north-1@vSBCr6TRbAzx7kNfepQd -p 4f8c105807ba8b39ed9a2325e067d0f72020c9ab9b089e3f8365e2a2be84f5a1 swr.cn-north-1.myhuaweicloud.com
步骤二：拉取镜像
docker pull swr.cn-north-1.myhuaweicloud.com/root/swr-demo-2048:latest
接下来，查看镜像是否已经下载到本地。
docker images
步骤三：修改组织

修改组织名称 millenario 创建组织
我们需要修改镜像的组织名，以便推送到个人组织内。
docker tag swr.cn-north-1.myhuaweicloud.com/root/swr-demo-2048:latest swr.cn-north-1.myhuaweicloud.com/millenario/swr-demo-2048:latest
步骤四：推送镜像到容器镜像服务-我的镜像

现在，我们可以将修改完组织的镜像，推送到容器镜像服务的仓库内。
docker push swr.cn-north-1.myhuaweicloud.com/millenario/swr-demo-2048:latest

docker login指令
docker login -u cn-north-1@vSBCr6TRbAzx7kNfepQd -p 4f8c105807ba8b39ed9a2325e067d0f72020c9ab9b089e3f8365e2a2be84f5a1 swr.cn-north-1.myhuaweicloud.com



echo from postgres:9.4 > Dockerfile-postgres
echo from redis:alpine > Dockerfile-redis



sed -i s/docker-server/${dockerServer}/g ./docker-compose-standalone.yml
sed -i s/docker-org/${dockerOrg}/g ./docker-compose-standalone.yml
sed -i s/image-version/${BuildNumber}/g ./docker-compose-standalone.yml

tar -zcvf docker-stack.tar.gz ./docker-compose-standalone.yml

```

B-Tree 的定义，可知检索一次最多需要访问 h 个节点。数据库系统的设计者巧妙利用了磁盘预读原理，将一个节点的大小设为等于一个页，这样每个节点只需要一次 I/O 就可以完全载入。每次新建节点时，直接申请一个页的空间，这样就保证一个节点物理上也存储在一个页里，加之计算机存储分配都是按页对齐的，就实现了一个节点只需一次 I/O。而检索的时候，一次检索最多需要 h-1 次 I/O（根节点常驻内存），其渐进复杂度为 $O(h)=O(log_dN)O(h)=O(log_dN)$，实际应用中，出度 d 是非常大的数字，通常超过 100，因此 h 非常小（通常不超过 3）。而红黑树这种结构，h 明显要深的多。由于逻辑上很近的节点（父子）物理上可能很远，无法利用局部性，所以红黑树的 I/O 渐进复杂度也为 O(h)，效率明显比 B-Tree 差很多。

B+Tree 是 的变种，有着比 B-Tree 更高的查询性能，其相较于 B-Tree 有了如下的变化：

有 m 个子树的节点包含有 m 个元素（B-Tree 中是 m-1）。
根节点和分支节点中不保存数据，只用于索引，所有数据都保存在叶子节点中。
所有分支节点和根节点都同时存在于子节点中，在子节点元素中是最大或者最小的元素。
叶子节点会包含所有的关键字，以及指向数据记录的指针，并且叶子节点本身是根据关键字的大小从小到大顺序链接。

LSM树（Log-Structured Merge Tree）存储引擎

代表数据库：nessDB、leveldb、hbase等

核心思想的核心就是放弃部分读能力，换取写入的最大化能力。LSM Tree ，这个概念就是结构化合并树的意思，它的核心思路其实非常简单，就是假定内存足够大，因此不需要每次有数据更新就必须将数据写入到磁盘中，而可以先将最新的数据驻留在磁盘中，等到积累到最后多之后，再使用归并排序的方式将内存内的数据合并追加到磁盘队尾(因为所有待排序的树都是有序的，可以通过合并排序的方式快速合并到一起)。

日志结构的合并树（LSM-tree）是一种基于硬盘的数据结构，与B-tree相比，能显著地减少硬盘磁盘臂的开销，并能在较长的时间提供对文件的高速插入（删除）。然而LSM-tree在某些情况下，特别是在查询需要快速响应时性能不佳。通常LSM-tree适用于索引插入比检索更频繁的应用系统。Bigtable在提供Tablet服务时，使用GFS来存储日志和SSTable，而GFS的设计初衷就是希望通过添加新数据的方式而不是通过重写旧数据的方式来修改文件。而LSM-tree通过滚动合并和多页块的方法推迟和批量进行索引更新，充分利用内存来存储近期或常用数据以降低查找代价，利用硬盘来存储不常用数据以减少存储代价。

磁盘的技术特性:对磁盘来说，能够最大化的发挥磁盘技术特性的使用方式是:一次性的读取或写入固定大小的一块数据，并尽可能的减少随机寻道这个操作的次数。


vi /lib/systemd/system/docker.service
ExecStart=/usr/bin/dockerd -H unix:///var/run/docker.sock -H tcp://0.0.0.0:2375 \

```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    #设置虚拟机的box
    config.vm.box = "centos7"

    config.vm.box_check_update = false
    #设置虚拟机的主机名
    config.vm.hostname = "centos7-01"

    #设置主机与虚拟机的共享目录
    #config.vm.synced_folder "./share", "/home/vagrant/share"
    
    #设置虚拟机IP地址Bridge模式
    config.vm.network "public_network", ip: "172.16.40.200", bridge: "WLAN"
    
    #Virtualbox相关配置
    config.vm.provider "virtualbox" do |v|
        #设置虚拟机的名称
        v.name = "centos701"

        #设置虚拟机的内存大小为2G
        v.memory = 2048

        #设置虚拟机的CPU个数
        v.cpus = 2
    end

    #使用shell脚本进行软件安装和配置
    config.vm.provision "shell", inline: <<-SHELL
        sudo yum -y install wget
        
        #  yum -y install lrzsz
        #  yum -y install gcc
        #  yum -y install gcc-c++
        #使用阿里的centos源
        sudo mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
        sudo wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
        #安装epel源
        sudo yum list | grep epel-release
        sudo yum install -y epel-release
        sudo wget -O /etc/yum.repos.d/epel-7.repo http://mirrors.aliyun.com/repo/epel-7.repo
        sudo yum clean all
        sudo yum makecache
        sudo yum repolist enabled
        sudo yum -y update
        #sudo yum repolist all
   
        #安装工具
        #sudo yum -y install git
        sudo yum -y install net-tools
        sudo yum -y install vim
        sudo yum -y install ntpdate
        #安装git
        sudo yum -y install curl-devel expat-devel gettext-devel openssl-devel zlib-devel asciidoc
        sudo yum -y install  gcc perl-ExtUtils-MakeMaker
        sudo cd /usr/local/src/
        sudo wget https://www.kernel.org/pub/software/scm/git/git-2.15.1.tar.xz
        sudo tar -vxf git-2.15.1.tar.xz
        sudo cd git-2.15.1
        sudo make prefix=/usr/local/git all
        sudo make prefix=/usr/local/git install
        sudo echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/profile
        sudo source /etc/profile

        #修改时区
        sudo ntpdate 218.186.3.36
        sudo timedatectl set-timezone Asia/Shanghai
        sudo echo "0 */2 * * * /usr/sbin/ntpdate -u ntp.api.bz > /dev/null 2>&1; /sbin/hwclock -w" >> /var/spool/cron/root
        
        #安装docker
        sudo wget -qO- https://get.docker.com | sh
        sudo yum remove docker \
                        docker-client \
                        docker-client-latest \
                        docker-common \
                        docker-latest \
                        docker-latest-logrotate \
                        docker-logrotate \
                        docker-selinux \
                        docker-engine-selinux \
                        docker-engine
        sudo yum install -y yum-utils device-mapper-persistent-data lvm2
        sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
        sudo yum makecache fast
        sudo yum -y install docker-ce
        sudo echo '{    "registry-mirrors": ["https://czcjm3w6.mirror.aliyuncs.com"]  }'>>/etc/docker/daemon.json
        #启动docker服务
        sudo  systemctl daemon-reload
        sudo systemctl start docker

        #设置docker服务启动后自运行
        sudo systemctl enable docker

        #添加vagrant用户添加到docker权限组
        sudo usermod -aG docker vagrant

        #拉取ssdb镜像
        sudo docker pull leobuskin/ssdb-docker
        sudo docker run -itd --name testssdb -p 8888:8888 leobuskin/ssdb-docker

        #清理包
        sudo yum clean all

    SHELL

end
```

在Ubuntu中，你可以像这样从PPA获得 Qt 5.9：

sudo add-apt-repository ppa:beineri/opt-qt591-trusty -y
sudo apt-get update -qq
sudo apt-get -y install qt59base qt59webengine
sudo apt-get -y install qt59webchannel qt59svg qt59location qt59tools qt59translations
source /opt/qt*/bin/qt*-env.sh
然后像这样编译和安装VNote：

cd vnote.git
mkdir build
cd build
qmake ../VNote.pro
make
sudo make install