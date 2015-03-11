FROM beetaa/nodejs:clean

RUN \
   npm install -g zedd && \
   npm cache clear

COPY ./zedd.conf /etc/supervisor/conf.d/zedd.conf

VOLUME /var/workspace

EXPOSE 7337

CMD supervisord -c /etc/supervisor/supervisord.conf 
