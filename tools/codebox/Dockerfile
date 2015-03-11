FROM beetaa/nodejs:latest

RUN \
   apt-get update && \
   apt-get install -y git && \
   npm install -g codebox@0.8.2 && \
   apt-get remove -y build-essential git && \
   rm -rf /var/lib/apt/lists/* && \
   apt-get clean && \
   npm cache clear

COPY ./codebox.conf /etc/supervisor/conf.d/

VOLUME /var/workspace

WORKDIR /var/workspace

EXPOSE 8001

CMD supervisord -c /etc/supervisor/supervisord.conf 
