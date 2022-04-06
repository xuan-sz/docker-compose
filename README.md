# docker-compose
使用docker-compose工具启动一些自己所需的服务
一、学习docker-compose的使用
	1.环境安装
		(1)安装docker,使用国内 daocloud 一键安装命令：
			curl -sSL https://get.daocloud.io/docker | sh
		(2)运行以下命令以下载 Docker Compose 的当前稳定版本：
			curl -L "https://github.com/docker/compose/releases/download/v2.2.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
		(3)测试是否安装成功：
			docker-compose --version
	2.常用命令
		(1)docker命令
			① docker images # 查看当前主机的所有镜像
			② docker search 镜像名 # 搜索镜像
			③ docker pull 镜像名 # 下载镜像，默认latest
			④ docker rmi -f 镜像名（或镜像id） # 删除镜像
			⑤ 删除所有容器和镜像
				docker container rm -f $(docker container ps -aq)
				docker system prune -a -f
			⑥ docker network ls	#可以查看网络列表，
			⑦ docker network inspect [容器id] #可以查看对应网络的配置
			⑧ docker network creact [网络名] #可以创建网络
			⑨ docker logs -f [container id] #像tail -f 监听日志
			① docker exec -it [容器名或者容器id] /bin/bash #进入容器,exit退出容器
		(2)	docker-compose命令
			① docker-compose up -d  #启动容器，-d表示在后台运行
			② docker-compose down 	#停止容器
			③ docker-compose logs -f #查看容器日志，-f表示自动更新
			④ docker-compose restart #重启容器，注意此操作可能不会重读部分配置文件
2.注意事项

