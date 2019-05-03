### 一、购买VPS
#### 选择vps
![select](https://github.com/skyloong/wow/blob/master/images/select.png)

选择$2.50的那个
#### 机房选择
![detail](https://github.com/skyloong/wow/blob/master/images/detail.png)

select location那里不选择洛杉矶和凤凰城就好了，因为这两个地方一般得不到可用IP

#### 查看IP和端口是否能用

![server](https://github.com/skyloong/wow/blob/master/images/server.png)
![info](https://github.com/skyloong/wow/blob/master/images/info.png)

复制IP地址

![port](https://github.com/skyloong/wow/blob/master/images/port.png)

看看22端口是否开放，不开放的就要更换IP
#### 更换IP
![switchIP](https://github.com/skyloong/wow/blob/master/images/switchIP.png)

点击更换IP，更换IP一次要$5

![changeIP](https://github.com/skyloong/wow/blob/master/images/changeIP.png)

其它上面的不用管，在最后Add a Message or Related Service那里告诉客服，爷要换5美元的IP要在中国能访问到的。然后他会给你邮箱发邮件，打开邮件付款就行了，只是可能要等一会。如果换了以后还是不行的话，就和客服沟通，让他换到能用的为止，当然了，这就不用再付钱了。

![tickets](https://github.com/skyloong/wow/blob/master/images/tickets.png)
![IPChange](https://github.com/skyloong/wow/blob/master/images/IpChange.png)

回到主页，点击那个tickets去和客服沟通，可以用谷歌翻译将中文翻译成英文和客服沟通。直到他给你换成能用的为止。
### 二、部署
要ssh连接到VPS，在win10下可以使用git bash。

[win10安装git](https://blog.csdn.net/qq_32786873/article/details/80570783)

![使用gitbash](https://github.com/skyloong/wow/blob/master/images/gitbash.png)
打开gitbash，使用以下命令
```
ssh -p22 root@IP地址
```
回车后要输入密码，密码在这
![密码](https://github.com/skyloong/wow/blob/master/images/info.png)
连接上VPS后输入以下命令
```
apt-get install curl -y
curl -sSL https://get.daocloud.io/docker | sh
curl -L https://github.com/docker/compose/releases/download/1.23.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
apt-get install git -y
git clone https://github.com/skyloong/skyv2.git
cd skyv2
apt-get install vim -y
vim server.config
```
将server.config里的参数替换
[在这里生成UUID](https://www.uuidgenerator.net/)

![UUID](https://github.com/skyloong/wow/blob/master/images/UUID.png)
最后在skyv2文件夹下运行命令
```
docker-compose up -d v2ray
```
到此VPS的搭建完成，用客户端连接看看能不能用。
