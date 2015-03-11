FROM beetaa/debian:git

RUN \
	apt-get update && \
	apt-get install -y autoconf build-essential && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*
