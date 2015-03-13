FROM beetaa/nodejs:clean
    
WORKDIR /

RUN apt-get update && apt-get install -y wget && \
    wget https://github.com/benweet/stackedit/archive/v4.3.11.tar.gz && \
    tar -xzf v4.3.11.tar.gz

WORKDIR  /stackedit-4.3.11

RUN npm install && \
    node_modules/bower/bin/bower install --allow-root --production --config.interactive=false

EXPOSE 3000

CMD nodejs server.js