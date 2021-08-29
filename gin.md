00. touch main.go
01. go mod init doc.leonmin.com 开启模块
02. go get github.com/gin-gonic 获取gin
03. r.Run(":5000") 监听5000端口
centos 安装 go
1. 下载 wget https://golang.google.cn/dl/go1.17.linux-amd64.tar.gz
2. 解压 tar xzf go1.17.linux-amd64.tar.gz
3. 环境变量 vim /ect/profile
export GOROOT=$HOME/go
export PATH=$HOME/go/bin:$PATH
export GOPROXY=https://goproxy.io,direct
4. 验证 go version
git 安装
1. 下载 wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.33.0.tar.gz
2. 解压 tar xzf git-2.33.0.tar.gz
3. cd git-2.33.0.tar.gz
4. ./configure
5. make && make install
6. git version
git 配置
1. ssh-keygen -t rsa -C "your email"
2. git config --global user.email "your email"
3. git config --global user.name "your name"
4. cat ~/.ssh/id_ras.pub

nginx 安装
1. 下载 wget http://nginx.org/download/nginx-1.20.1.tar.gz
2. 解压 tar xzf nginx-1.20.1.tar.gz
3. cd nginx-1.20.1.tar.gz
4. ./configure
5. make && make install
6. 环境变量 vim /ect/profile
export PATH=/usr/local/nginx/sbin:$PATH
7. /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
8. nginx -v
nginx 配置
