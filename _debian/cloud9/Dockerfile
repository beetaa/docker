FROM beetaa/nodejs:latest

RUN \
  git clone https://github.com/c9/core.git /cloud9 && \
  cd /cloud9 && \
  scripts/install-sdk.sh && \
  rm -rf /tmp/* && rm -rf /var/tmp/* && \
  npm cache clear

VOLUME /var/workspace

EXPOSE 8181

WORKDIR /cloud9

CMD ["node", "server.js",  "-w", "/var/workspace", "-a", "beetaa:beetaa"]
