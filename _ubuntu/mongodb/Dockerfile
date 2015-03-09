FROM beetaa/ubuntu:latest
MAINTAINER beetaa <beetaa@outlook.com>

# 安装、配置 MongoDB

RUN \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 && \
  echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' > /etc/apt/sources.list.d/mongodb.list && \
  apt-get update && \
  apt-get install -y mongodb-org && \
  apt-get -y clean && \
  rm -rf /tmp/* && rm -rf /var/tmp/* && rm -rf /var/lib/apt/lists/*
  
# 定义数据集目录

VOLUME ["/data/mongodb"]

# 定义端口

EXPOSE 27017
EXPOSE 28017

COPY start.sh /data/mongodb/start.sh

RUN chmod a+x /data/mongodb/start.sh

# 开机进入命令行

CMD ["/data/mongodb/start.sh"]