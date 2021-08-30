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
9. nginx -t

安装gcc依赖 https://www.cnblogs.com/gyfluck/p/10537436.html
wget ftp://gcc.gnu.org/pub/gcc/infrastructure/gmp-6.1.0.tar.bz2
tar -jxvf gmp-6.1.0.tar.bz2
cd gmp-6.1.0
./configure
make && make install

wget ftp://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2
tar -jxvf mpfr-3.1.4.tar.bz2
cd mpfr-3.1.4
./configure
make && make install

wget ftp://gcc.gnu.org/pub/gcc/infrastructure/mpc-1.0.3.tar.gz
tar -zxvf mpc-1.0.3.tar.gz
cd mpc-1.0.3
./configure
make && make install

安装gcc https://www.imqianduan.com/linux/525.html
wget http://ftp.gnu.org/gnu/gcc/gcc-9.2.0/gcc-9.2.0.tar.gz
tar xzf gcc-9.2.0.tar.gz
cd gcc-9.2.0.tar.gz
./configure -enable-checking=release -enable-languages=c,c++ -disable-multilib
make && make install
find / -name "libstdc++.so*"
cp /root/gcc-9.2.0/stage1-x86_64-pc-linux-gnu/libstdc++-v3/src/.libs/libstdc++.so.6.0.27 /usr/lib64
cd /usr/lib64
rm -rf libstdc++.so.6
ln -s libstdc++.so.6.0.27 libstdc++.so.6

node.js 安装
1. wget https://npm.taobao.org/mirrors/node/v14.17.5/node-v14.17.5-linux-x64.tar.gz
2. tar xzf node-v14.17.5-linux-x64.tar.gz
3. vim /etc/profile
export PATH=$HOME/node-v14.17.5-linux-x64/bin:$PATH
4. source /etc/profile

android12 安装
https://developers.google.cn/android/ota
0. 下载android12 OTA 镜像 https://developer.android.google.cn/about/versions/12/download-ota#images
1. 安装android sdk platform-tools, https://developer.android.google.cn/studio/releases/platform-tools.html
2. 环境变量 export PATH=$PATH:$HOME/your_path/platform-tools
3. 确保没有OTA更新, Settings > About phone > System updates  应该是 "您的系统是最新的"
4. 连接手机, 启用USB调试, 执行 adb reboot recovery 进入恢复模式
5. 按住电源键再按一次音量加键打开恢复文本菜单
6. 选择 Apply update from ADB 项
7. 运行 adb devices 检查设备名称旁边是否显示 sideload
8. 运行 adb sideload ota_file.zip
9. 选择 Reboot system now

iterm2 ssh 自动断开
1. 客户端 sudo vim /etc/ssh/ssh_config
ServerAliveInterval 60
2. 服务端 sudo vim /etc/ssh/sshd_config
ClientAliveInterval 600
ClientAliveCountMax 10


