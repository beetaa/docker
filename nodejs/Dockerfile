FROM beetaa/ubuntu:latest
MAINTAINER beetaa <beetaa@outlook.com>

# 安装、配置 Nodejs

RUN \
  cd /tmp && \
  wget http://nodejs.org/dist/node-latest.tar.gz && \
  tar xvzf node-latest.tar.gz && \
  rm -f node-latest.tar.gz && \
  cd node-v* && \
  ./configure && \
  CXX="g++ -Wno-unused-local-typedefs" make && \
  CXX="g++ -Wno-unused-local-typedefs" make install && \
  cd /tmp && \
  rm -rf /tmp/node-v* && \
  npm install -g npm && \
  echo -e '\n# Node.js\nexport PATH="node_modules/.bin:$PATH"' >> /root/.bashrc

# 安装 Nodejs 库

RUN \
  npm install -g gulp mocha nodemon puer mongoose redis && \
  rm -rf /tmp/* && rm -rf /var/tmp/*

# 开机进入命令行

CMD ["bash"]