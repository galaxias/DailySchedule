# 安装 python

sudo yum install python3

## 拷贝

文件
scp 源 目的
文件夹
scp -r

服务器 格式  用户名@地址:路径

源 地址  路径


## 配置 qemu 

./configure --prefix=/home/zcore/software/qemu_installed --target-list=x86_64-softmmu,riscv64-softmmu --enable-kvm 


## 设置环境变量
echo 'export PATH=$PWD/x86_64-softmmu:$PWD/riscv64-softmmu:$PATH' >> /home/zcore/.bashrc



## systemd


列出 Linux 系统上的所有单元
systemctl list-unit-files

限制输出列表只包含服务
systemctl list-unit-files --type=service


https://blog.csdn.net/weixin_37766296/article/details/80192633


## 用户 与 组 

查看用户组
vi /etc/group

1. 添加一个用户组并指定id为1002

sudo groupadd －g 1002 www

 

2. 添加一个用户到www组并指定id为1003

sudo useradd wyx -g 1002 -u 1003 -m

 

3. 修改用户的密码

sudo passwd wyx

 

4. 删除一个用户

sudo userdel wyx

 

5. 为该用户添加sudo权限

sudo usermod -a -G adm wyx

sudo usermod -a -G sudo wyx

 

6. 查看所有用户和用户组：

cat /etc/passwd

cat /etc/group


用户
```txt
用户名：密码占位符（x 表示用户需要密码登录）：用户标识号（UID）：
组标识号（GID）：注释性描述：主目录：登录的 shell
```


看密码

 sudo cat /etc/shadow

```txt
-c	指定一段注释性描述
-d	指定用户主目录
-md	如果指定的用户主目录不存在，则用此选项来创建目录并指定为主目录
-g	指定用户所属的主用户组
-G	指定用户所属的附加用户组
-s	指定用户的登录 shell
-u	指定用户的用户号，若有 -o 选项，则可以重复使用其它用户的标识号

```


5、userdel 删除用户
-r 选项顺便删除主目录

sudo userdel haha


### 组 
组名 : 口令 : 组标识号（GID）：组内用户列表（多用户可用逗号分隔开）



./config.sh --url https://github.com/rcore-os/zCore --token ADKUL4N2C5AGQ3STHCMNKRS7CA2E4



// bash
https://www.cnblogs.com/cosiray/archive/2012/03/02/2377099.html





## git

　wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.27.0.tar.gz


　tar -zxvf git-2.8.3.tar.gz


　　　　cd git-2.8.3

./configure prefix=/usr/local/git/

make && make install

git --version

vi /etc/profile

export PATH=$PATH:/usr/local/git/bin

　source /etc/profile


sudo rm -rf git*

which -a git