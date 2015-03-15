FROM debian:wheezy

RUN \
   apt-get update && \
   apt-get install -y curl supervisor && \
   sed -i 's/^\(\[supervisord\]\)$/\1\nnodaemon=true/' /etc/supervisor/supervisord.conf && \
   curl -sL https://deb.nodesource.com/setup | bash - && \
   apt-get install -y nodejs && \
   npm install -g npm && \
   apt-get remove -y curl && \
   apt-get clean && \
   npm cache clear && \
   rm -rf /tmp/* && rm -rf /var/tmp/* && rm -rf /var/lib/apt/list/*

CMD ["bash"]
