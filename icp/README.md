# Docker

## Installation docker ce
### Mac
https://docs.docker.com/docker-for-mac/install/

### Windows
https://docs.docker.com/docker-for-windows/install/


## Sign up docker hub's account
    访问网站注册docker hub账号
    https://hub.docker.com
    注册完成后，在本机docker登录

## docker 常用命令

### images 常用命令
* 在docker hub上搜索images
    docker search <images name>
    Example: docker search tomcat

* 拉去镜像
    docker pull username/repository<:tag_name>
    Example: docker pull tomcat

* 列出机器上的镜像
    docker images
    yanfa-mbp:~ yanfaz$ docker images | grep tomcat
    tomcat                          latest                         11df4b40749f        2 weeks ago         558MB


* 删除镜像
    docker rmi <image id> or <image name:tag name>
    Example: docker rmi tomcat  or docker rmi 11df4b40749f

### container 常用命令

启动容器docker run
在容器中运行"echo"命令，输出"hello word"  
docker run image_name echo "hello word"  

交互式进入容器中
docker run -i -t <image_name or image_id> /bin/bash

后台运行
docker run -d <image_name or image_id>

暴露端口 宿主机port:容器port
docker run -p 8181:8080 <image_name or image_id>

查看日志
docker logs <container_id or container_name>

查看正在运行的container
docker ps

查看所有container
docker ps -a

运行/停止/重启容器
docker start/stop/restart <container_id or container_name>

进入容器
docker exec -it <container_id or container_name> /bin/bash

### 创建images

定义Dockerfile文件
#######todo。。。。。

创建images
docker build -t <images_name>:<tag_name> .

推送images
docker push username/<image_name>:<tag_name>

标签images
docker tag <images_name>:<tag_name> <new_images_name>:<new_tag_name>
Example: docker tag tomcat yanfaz:1.0

