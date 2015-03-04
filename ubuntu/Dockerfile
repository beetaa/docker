FROM ubuntu:14.04
MAINTAINER beetaa <beetaa@outlook.com>

# 更换为国内源

COPY etc/apt/sources.list /etc/apt/sources.list

# 安装基本软件

RUN \
  apt-get update && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y curl git unzip vim wget && \
  apt-get install -y python python-pip && \
  apt-get -y clean && \
  rm -rf /tmp/* && rm -rf /var/tmp/* && rm -rf /var/lib/apt/lists/*

# 用户使用设置

ADD root/.gitconfig /root/.gitconfig

# 设置环境变量

ENV HOME /root

# 定义初始目录

WORKDIR /root

# 开机进入命令行

CMD ["bash"]