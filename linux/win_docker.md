# 1. windows
我们的这个镜像现在只是一个最基本的ubuntu的系统，里面很多工具都没有，如ping、ifconfig、wget、vim等，也没有python。接下来我们把这些一个一个都装上。

由于镜像默认用的是ubuntu官方的源，从国内连官方的源很慢，我们先把源改成163的源。修改/etc/apt/sources.list的内容为下面的内容

deb http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
运行

apt update
接下来，安装ping，wget，ifconfig，vim等工具

apt install iputils-ping wget net-tools vim


安装python3.6

apt install python3.6
ln -s /usr/bin/python3.6 /usr/bin/python
安装pip

apt install python3-pip


配置VIM
安装完工具后，我们来配置一下vim。打开~/.vimrc文件，输入vim的配置。比如我的配置是这样的

set ru
syntax on
set background=dark
set sw=4
set ts=4
set tabstop=4
set shiftwidth=4
set expandtab
filetype plugin on
set autoindent
set smartindent
set number
set viminfo='10,\"100,:20,%,n~/.viminfo
function! ResCur()
    if line("'\"") <= line("$")
        normal! g`"
        return 1
    endif
endfunction

augroup resCur
    autocmd!
    autocmd BufWinEnter * call ResCur()
augroup END

highlight WhiteSpaces ctermbg=green guibg=#55aa55
match WhiteSpaces /\s\+$/
好了，至此，我们的开发环境配置好了。



## 1.1. 提交镜像
为方便以后的使用，我们把这个配置好的容器打成一个新的镜像。在容器中执行exit退出，我们现在来到了windows的命令行窗口。我们查看一下我们刚刚配置好的容器，运行

docker ps -a
输出

CONTAINER ID        IMAGE                       COMMAND             CREATED             STATUS                      PORTS               NAMES
39ca895c725e        ubuntu:18.04                "bash"              3 hours ago         Exited (0) 19 seconds ago                       relaxed_wiles


运行下面的命令，提交更改，将容器打包成一个新的镜像

docker commit 39ca895c725e shenzhongqiang/python-dev:version1
我们再来查看一下本地的镜像

docker images
输出

REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
shenzhongqiang/python-dev   version1            fbf0ce58d00d        2 minutes ago       542MB
ubuntu                      18.04               93fd78260bd1        6 days ago          86.2MB
可以看到，现在我们本地有2个镜像了。下面一个是原始的docker hub上的ubuntu镜像，上面一个就是我们自己定制的镜像。

之后我们就可以基于我们定制的镜像，启动容器做开发了。启动容器很简单，只要运行

docker run -it fbf0ce58d00d bash
需要注意的是，容器如果被删除了，其中的更改也会丢失。要保存容器中的更改，需要像上面这样把更改commit到镜像中。



好，以上就是定制的所有步骤。这两天我逐渐把项目迁移到容器里了，在容器里开发感觉比在虚拟机里开发顺滑多了。



## 1.2. 为方便起见，上面这个镜像放在了我的docker hub上，大家可以通过下面的命令获取
[win_docker](https://link.zhihu.com/?target=https%3A//download.docker.com/win/stable/Docker%2520for%2520Windows%2520Installer.exe)
docker pull shenzhongqiang/python-dev:version1
镜像加速器
https://czcjm3w6.mirror.aliyuncs.com



# 2. linux
新版的 Docker 推荐使用 json 配置文件的方式，默认为 /etc/docker/daemon.json，非默认路径需要修改 dockerd 的 –config-file，在该文件中加入如下内容： { "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"] }

