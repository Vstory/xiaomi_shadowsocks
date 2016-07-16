# xiaomi_shadowsocks
小米路由器安装shadowsocks教程及源码

# 开启ROOT权限
安装shadowsocks需要开启SSH权限
- 如果是青春版，只需要刷开发版rom就可以，下载地址http://www1.miwifi.com/miwifi_download.html 点击rom->ROM for Lite 开发版(尽量使用IE下载，坑爹的小米有兼容性问题)  
- 其他版本路由器详细开启方法可看官方教程：http://d.miwifi.com/rom/ssh

#获取root密码
如果是刷了开发版获取root的话才需要这一步  
需要MT7620 MT7621 MT7628 芯片上面运行，  
找一个这种芯片的路由运行 或者 让有这种路由的人帮你算密码(小米mini,极路由，newifi,优酷等都可以).  
把本库中的sn目录下的2个文件夹复制到路由器的某个目录
执行
```
chmod +x sn
```
然后执行
```
./sn [sn]
```
[sn]是你的路由器序列号，一般在路由器机身上，比如我的10508/00360***  
执行后会输出你的路由器root密码  

如果没有额外的路由来得到密码，还有一种方法直接修改root密码，登录miwifi.com进入路由器管理页  
地址类似这样
```
http://miwifi.com/cgi-bin/luci/;stok=...f84c3bd40b7/web/home#router
```
把/web/home#router换成/api/xqsystem/set_name_password?oldPwd=[你的旧登录密码]&newPwd=[新密码] 然后回车
如果输出{"code":0}代表成功，这样路由器的管理密码和root密码都变成了[新密码]，千万别搞丢了  

待续
