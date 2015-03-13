FROM beetaa/nodejs:clean

RUN apt-get update && apt-get install -y git-core && \
    git clone https://github.com/benweet/stackedit.git

WORKDIR stackedit

RUN npm install && \
    node_modules/bower/bin/bower install --allow-root --production --config.interactive=false

EXPOSE 3000

CMD nodejs server.js