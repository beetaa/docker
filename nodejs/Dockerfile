FROM beetaa/nodejs:clean

RUN \
   apt-get update && \
   apt-get install -y build-essential && \
   npm install -g gulp mocha forever nodemon puer mongoose redis && \
   apt-get clean && \
   npm cache clear && \
   rm -rf /tmp/* && rm -rf /var/tmp/* && rm -rf /var/lib/apt/list/*

CMD ["bash"]
