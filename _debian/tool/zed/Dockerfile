FROM beetaa/nodejs:latest

RUN \
   apt-get update && \
   apt-get install -y supervisor && \
   npm install -g zedd && \
   touch /etc/supervisor/conf.d/zedd.conf && \
   echo "[program:zedd]" >> /etc/supervisor/conf.d/zedd.conf && \
   echo "command=zedd --user beetaa --pass beetaa --root /var/workspace --remote --enable-run" >> /etc/supervisor/conf.d/zedd.conf && \
   apt-get clean && \
   npm cache clear

VOLUME /var/workspace

EXPOSE 7337

CMD supervisorctl reload
