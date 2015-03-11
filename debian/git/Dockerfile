FROM beetaa/debian:curl

COPY ./.gitconfig /root/.gitconfig

RUN \
	apt-get update && \
	apt-get install -y git && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*
