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

