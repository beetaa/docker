FROM beetaa/nodejs:latest

RUN \
   apt-get update && \
   apt-get install -y git software-properties-common python python-pip && \
   git clone https://github.com/c9/core.git /cloud9

WORKDIR /cloud9

RUN apt-get install -y tmux curl

RUN \
   scripts/install-sdk.sh && \
   rm -rf /tmp/* && rm -rf /var/tmp/* && \
   npm cache clear && \
   apt-get remove -y build-essential software-properties-common python-pip git && \
   apt-get clean

VOLUME /var/workspace

EXPOSE 8181

COPY ./cloud9.conf /etc/supervisor/conf.d/

CMD supervisord -c /etc/supervisor/supervisord.conf
