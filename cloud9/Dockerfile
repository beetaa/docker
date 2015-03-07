FROM beetaa/nodejs:latest
MAINTAINER beetaa <beetaa@outlook.com>

# 安装 Cloud9

RUN \
  git clone https://github.com/c9/core.git /cloud9 && \
  cd /cloud9 && \
  scripts/install-sdk.sh && \
  mkdir /workspace

VOLUME /workspace

EXPOSE 8181

WORKDIR /cloud9

# 清除临时文件

RUN rm -rf /tmp/* && rm -rf /var/tmp/*

# 开机进入命令行

CMD ["node", "server.js",  "-w", "/workspace", "-a", "beetaa:beetaa"]