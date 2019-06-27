Docker

```shell
安装Docker维护的版本
sudo apt-get install -y curl
curl -sSL https://get.docker.com/ubuntu/ |sudo sh
docker run ubuntu echo 'Hello world'
```

```shell
使用非root用户：
sudo groupadd docker
sudo gpasswd -a ${USER} docker
sudo service docker restart 
```

```shell
#启动交互式容器
docker run -i -t ubuntu /bin/bash
--name=container01
#后台运行
ctrl+P ctrl+Q
#附加到交互式容器
docker attach {name}
#查看容器：
docker ps 
docker ps -a
#最新
-l
docker inspect {id/name}
#重新启动已停止容器
docker start [-i] 容器名
#删除已经停止容器
docker rm [容器名]
```

```shell
#启动守护式容器
docker run --name dc1 -d ubuntu /bin/sh -c "while true;do echo hello world;sleep 1;done"
#查看容器日志
docker logs [-f] [-t] [--tail] 容器名
docker logs -tf --tail 0 dc1
#查看容器进程
docker top dc1
#在运行中容器进行多个进程
docker exec -i -t dc1 /bin/bash
#停止守护式容器
docker stop 容器名
docker kill 容器名
```

Nginx部署流程

1. 创建映射80端口的交互式容器
2. 安装Nginx
3. 安装文本编辑器vim
4. 创建静态页面
5. 修改Nginx配置文件
6. 运行Nginx
7. 验证网站访问

```shell
#设置容器的端口映射
docker run -p 80 --name web -i -t ubuntu /bin/bash
apt-get install -y nginx
apt-get install -y vim
mkdir -p /var/www/html
cd /var/www/html
vim index.html
whereis nginx
ls /etc/nginx/sites-enabled
vim default
改root /var/www/html
#查看端口映射情况
docker port web
curl http://ip:映射端口
docker inspect看IPAddress
#启动（重启容器时ip和端口可能变化）
docker exec web nginx
```

**xmind**