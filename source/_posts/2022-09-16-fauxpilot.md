---
title: 本地搭建FauxPilot服务，实现代码生成
date: 2022-09-16 21:52:10
tags:
-备忘录
---
# 根据[[FauxPilot]](https://github.com/moyix/fauxpilot)的文档开始搭建

# 首先根据文档检查必备环境

1.  检查电脑GPU算力是否大于等于7，[[在这里可以查看]](https://developer.nvidia.com/zh-cn/cuda-gpus#compute)

    a.  实测显存至少要6G

    b.  20系显卡无论是台式还是笔记本算力都大于等于7，其他的都低于要求

2.  该项目只支持Linux环境，[[Windows需要启用wsl，且确保版本是wsl2]](https://docs.microsoft.com/zh-cn/windows/wsl/install)

# 然后配置软件环境

1.  安装Docker，docker-compose

    a.  wsl没有sysctl服务，不能以此启动docker守护进程，要每次手动启用

2.  安装[[nvidia-docker]](https://github.com/NVIDIA/nvidia-docker)

3.  确保安装了nvidia驱动和cuda驱动，Windows需要安装wsl[[定制驱动]](https://docs.nvidia.com/cuda/wsl-user-guide/index.html)

    a.  显卡驱动只要确保在主机安装了GFD驱动即可

4.  确保安装了curl和zstd

# 启动脚本

-   个人在启动脚本时遇到过一些问题,/bin/bash目录找不到，这个时候可以用dos2unix转换一下脚本的换行

-   启动脚本，使用文档给出的示例检查返回结果

-   因为wsl2的ip是独立于本机的，启动之后Windows需要配置脚本获取wsl的ip

    -   可以在在wsl种加入启动命令，将wsl本机ip映射为hosts中的地址

-   实测GitHub Copliot扩展配置debug命令无法链接，推荐使用fauxcopilott
