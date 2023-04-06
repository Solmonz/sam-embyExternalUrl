# embyExternalUrl

### emby调用外部播放器服务端脚本:

通过nginx的njs模块运行js脚本,在emby视频的外部链接处添加调用外部播放器链接，所有emby官方客户端可用

![](https://github.com/Solmonz/sam-embyExternalUrl/blob/32c01ea2541f3605771c8330ce2853b1fce9b0f2/emby.png)

使用方法:

这里采用的是docker安装,也可以不使用docker,自己安装njs模块

先下载脚本:
```bash
wget https://github.com/Solmonz/sam-embyExternalUrl/releases/download/v0.0.1/addExternalUrl.tar.gz && mkdir -p ~/embyExternalUrl && tar -xzvf ./addExternalUrl.tar.gz -C ~/embyExternalUrl && cd ~/embyExternalUrl
```

然后看情况修改externalUrl.js文件里面的serverAddr

tags 和 groups是从视频版本中提取的关键字作为外链的名字,不需要就不用改

emby.conf默认反代emby-server是本机的8096端口,按需修改

docker-compose.yml默认映射8097端口,按需修改

然后启动docker
```
docker-compose up -d
```
访问8097端口,在视频信息页面的底部就添加了外部播放器链接

日志查看:
```
docker logs -f  embyUrl-nginx 2>&1 | grep error
```
### emby调用外部播放器油猴脚本,只支持网页:

[油猴地址](https://greasyfork.org/en/scripts/459297-embylaunchpotplayer)

网络收集 如有侵犯 立即删除

