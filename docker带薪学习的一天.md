## docker带薪学习的一天

##### 一、基本命令

1、docker安装：yum install -y docker

2、docker启动：sudo systemctl start docker

3、docker启动状态查看：systemctl status docker

4、docker查看正在运行的容器：docker ps

5、docker切换aliyun镜像源

##### 二、镜像搜索、拉取操作

6、搜索镜像：docker search ***

7、docker pull + 镜像名称NAME字段

8、docker images 查看当前镜像

9、docker ps 查看当前运行容器 -a（表示正在运行的和已经结束的）

##### 三、实际运行容器

**10、交互式运行：**docker run -it 容器名 解释器 

-i参数表示以交互式模式运行容器，-t参数表示为容器重新分配一个伪终端

例如：docker run -it docker.io/centos /bin/bash

执行后，会进入docker容器的终端， exit为退出方式。

-d参数表示控制docker容器在后台运行。

-c参数表示使该镜像在后台执行-c参数后面指定的命令，

docker run -d docker.io/centos /bin/bash -c "while true; do echo 'Hello World '; sleep 1; done"

11、docker 日志查看

docker logs + 容器ID

12、docker容器的关闭

docker stop + 容器ID 等待处理完数据再杀死

docker kill + 容器ID 直接杀死

docker rm + 容器ID 删除关闭状态的容器

13、docker容器的再次终端进入

docker attach + 容器ID

docker exec -it 容器ID + 解释器（/bin/bash）

##### 四、端口映射

14、我们的Docker容器内，要开放指定端口，以向外提供服务，这时，就需要我们配置Docker镜像的端口映射。

docker run -d -p 【物理机端口号】:【容器端口号】 【容器名】 

docker run -d -p 80:80 docker.io/httpd

##### 五、docker数据映射

Docker的数据映射使用-v参数来设定，与之前介绍的-p参数类似，-v参数后面先跟本地的一个目录，然后跟冒号，后面再跟Docker容器内的某个目录。
Docker数据映射命令示例如下：

docker run -d -p 80:80 -v /var/www/html/:/usr/local/apache2/htdocs/ docker.io/httpd

echo "docker Apache" > /var/www/html/index.html