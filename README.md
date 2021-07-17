本脚本源自A大，在他基础上做了小小修改，主要是解决证书申请的问题！

一、使用一键脚本安装
复制以下命令在VPS中执行，选择安装trojan，然后输入解析到VPS的域名并回车（不要带http://，只输入域名，例如atrandys.com或者xxx.atrandys.com），开始安装，然后等待安装完成即可。
注意：如果提示SELinux状态问题，请按要求输入Y重启VPS，然后再执行本脚本，否则可能https证书申请出错

curl -O https://raw.githubusercontent.com/guolongchu/trojan/master/trojan_mult.sh && chmod +x trojan_mult.sh && ./trojan_mult.sh

另外建议安装bbr，来源于网络分享，以下脚本安装，建议用原版bbr加速，不赘述了

二、电脑上其他软件如何使用Trojan
1、如果软件支持配置socks5，直接指向127.0.0.1：1080即可。
2、如果软件不支持配置socks5，可选择sstap/sockscap64/supercap等软件，曲线实现代理。
常见问题总结
1、Trojan客户端打开无法运行，提示缺少找不到vcruntime140.dll或找不到msvcp140.dll。
原因缺少运行库，点击下载链接中的两个软件，一个是32位一个是64位，请全部安装即可。
2、如果遇到vcruntime140_1的错误，下载下面的文件放到C:\windows\system32目录下即可
点击下载140_1.dll
3、trojan服务端怎么修改密码
trojan服务端配置文件路径如下，如需修改内容，修改以下文件即可。
/usr/src/trojan/server.conf
修改完成后，重启trojan服务端即可，同时客户端的密码也要同步修改哦。
systemctl restart trojan
