FROM beetaa/nodejs:clean

RUN npm install -g puer nodemon prez && \
    npm cache clear

# supervisor 配置文件路径，文件到文件
VOLUME /etc/supervisor/conf.d/app.conf

# 程序路径
VOLUME /app
WORKDIR /app

# puer 缺省端口
EXPOSE 8000
# 一般程序缺省端口
EXPOSE 3000

CMD ["bash"]