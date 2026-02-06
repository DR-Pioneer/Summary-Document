### anaconda带薪学习的一天

本机安装anaconda地址：C:\Users\34244\anaconda

conda --version 查看环境变量是否设置成功

##### 1、虚拟环境的管理

Activate 默认进入自带base环境

##### 2、创建虚拟环境

conda create -n 虚拟环境名称 python=python版本

例：conda create -n python310 python=3.10

##### 3、查看虚拟环境列表

conda env list

##### 4、切换至虚拟环境

activate 虚拟环境名称

conda deactivate 离开虚拟环境

##### 5、卸载虚拟环境

conda remove --name 虚拟环境名称 --all

##### 6、安装、卸载第三方包

conda install request

pip install request

conda remove request

pip uninstall request

##### 7、查看环境包信息

conda list

##### 8、conda 添加国内源

查看现有源

conda config --show-sources

添加清华源

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/

删除默认源 

conda config --remove channels defaults

设置搜索时显示通道地址

conda config --set show_channel_urls yes

##### 9、pip 与 conda的区别

pip install是安装这些待编译的内容，主要体现的是根据当前的环境进行灵活的调整，有时候要下载源代码在本地进行编译，形成whl，有时候则是直接下载whl来完成目标。
而conda install则是直接下载对应的二进制文件，我们需要使用的pylint.exe，这需要我们使用conda install，所以我们使用conda install。









