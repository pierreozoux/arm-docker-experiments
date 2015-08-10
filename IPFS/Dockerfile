FROM resin/armv7hf-debian:jessie

EXPOSE 4001 5001 8080
ENV IPFS_PATH /data/ipfs
ADD start_ipfs /usr/local/bin/start_ipfs
VOLUME /data/ipfs

RUN apt-get update \
&&  apt-get install -y --no-install-recommends \
      ca-certificates \
      apt-utils \
      wget \
      unzip \
&&  rm -rf /var/lib/apt/lists/* \
&&  wget https://gobuilder.me/get/github.com/ipfs/go-ipfs/cmd/ipfs/ipfs_master_linux-arm.zip \
&&  unzip ipfs_master_linux-arm.zip \
&&  mv ipfs/ipfs /usr/local/bin/ \
&&  chmod 755 /usr/local/bin/start_ipfs

ENTRYPOINT ["/usr/local/bin/start_ipfs"]
