FROM beetaa/debian:git

RUN \
   git clone https://github.com/c9/core.git /cloud9 && \
   apt-get update && \
   apt-get install -y build-essential software-properties-common python python-pip

WORKDIR /cloud9

RUN \
   curl -sL https://deb.nodesource.com/setup | bash - && \
   apt-get install -y nodejs && \
   curl -L https://npmjs.com/install.sh | sh

RUN apt-get install -y tmux 

RUN \
   git checkout a356105c7914d57505eb066f3b7e469951c6aaad && \
   scripts/install-sdk.sh && \
   rm -rf /tmp/* && rm -rf /var/tmp/* && \
   npm cache clear && \
   apt-get remove -y build-essential software-properties-common && \
   apt-get clean

VOLUME /var/workspace

EXPOSE 8181

CMD node server.js -w /var/workspace -a beetaa:beetaa
