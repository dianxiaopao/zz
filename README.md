### 部署前的准备

#### VPS服务器购买

推荐这款
[1G/1C/20G SSD/4T $10.29/年 (LEB专属)](https://my.racknerd.com/aff.php?aff=4440&pid=810)

按照真实信息注册，邮箱要真实，可以使用支付宝支付。
VPS开通后，查看root密码和控制面板的账户名和密码：
打开 Email 訊息紀錄，在邮件名是 KVM VPS Login Information 的邮件里。

IP若开机就被墙的，购后的72小时内支持免费更换一次,72小时后换ip需要收费。


#### 域名购买、托管到CloudFlare

域名注册、购买，推荐使用namesilo，免费的whois隐私保护！
- NameSilo官网（域名）： [namesilo官网](https://www.namesilo.com)
- PING工具：[ping工具（检测解析域名是否生效）](https://ping.chinaz.com/)
- CloudFlare(套CDN)[：CF官网](https://www.cloudflare.com/zh-cn/)

#### SSH 链接工具
  任选其中一个即可
 - putty(非常小巧)：[putty](https://putty.org/)
 - FinalShell(全平台):[FinalShell下载](https://www.hostbuf.com/t/988.html)

### 部署环节
 安装V2Ray 以Ubuntu 20+ 为例,centos 慎用
#### 必要更新操作(Debian/Ubuntu)
```
 apt update -y && apt install -y curl socat wget
```
防火墙操作,大部分国外主机厂商仅有机器防火墙，只需要在机器上开启防火墙即可，国内厂商主机需要再web控制台防火墙栏目开放端口
```
ufw allow 22
ufw allow 443
ufw --force  enable
ufw reload
      
```

#### 正式安装V2Ray
```
bash <(wget -qO- -o- https://git.io/v2ray.sh)
```

#### 管理面板
安装完成后，输入 v2ray 就能看到管理面板

V2Ray 脚本管理面板 提示，如果你不想执行任何功能，直接按 Enter 回车退出即可。

#### BBR加速
```
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
```


### 多客户端验证使用环节
#### 客户端下载
- V2Ray-windows客户端：[v2rayN下载](https://github.com/2dust/v2rayN/releases)
- 安卓：[V2RayNG](https://github.com/2dust/v2rayNG)
- 苹果MAC OS：[V2RayU下载](https://github.com/yanue/V2rayU/releases)
- IOS：App Store中，登录非国区账号，安装Shadowrocket小火箭（推荐，协议支持全面、便宜）
不管是iPad平板还是iPhone手机，比较推荐的科学上网软件必定是：Shadowrocket，但是需要注册一个非国区或美区账号才能进行购买，目前是2.99美刀约20块人民币，注册美区账号和充值购买也非常简单，请参考以下两篇文章。
- 如何注册美区Apple ID:https://zhuanlan.zhihu.com/p/635054054
- 美区账号如何充值：https://zhuanlan.zhihu.com/p/636121931
