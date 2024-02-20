# Col .1 上手使用

## 1. 网络连接

### 有线连接

- `ip addr` 可以查看网络状态
- `ifup [网卡名称]` 启动网卡
  - 再次查看网络状态，如果分配了ip，表示网卡启动正确
- `vi /etc/sysconfig/network-scripts/ifcfg-[网卡名称]` 修改`ONBOOT=yes`  设置开机自启动

### 无线连接

### 端口开放

- `sudo firewall-cmd --zone=public --add-port=[port]/tcp --permanent` 开启端口（notion: 开启后需重启firewalld）
- `firewall-cmd --list-ports` 查看开放端口号

### 固定IP

- `vi /etc/sysconfig/network-scripts/ifcfg-[网卡名称]` 新增两行`IPV6ADDR` `IPV6_DEFAULTGW` 网关地址和地址前缀可以去路由器后台查询

## 2. yum源配置

```shell
# 阿里云的yum源：
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
### 再配置一个epel源：
wget  -P /etc/yum.repos.d/  https://mirrors.aliyun.com/repo/epel-7.repo
yum makecache
```

## 3. oh my zsh 安装

### 一键安装

``` shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 无科学上网安装

```shell
# 提前下载https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
/bin/zsh install.sh
```

## 4. 调整终端分辨率

# Col .2 文件互传

## 1. vsftpd安装

``` shell
yum install vsftpd # 安装
chkconfig vsftpd on # 开机启动
service vsftpd start # 启动
```



## 2. 允许远程用户登陆



