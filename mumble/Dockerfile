FROM resin/armv7hf-debian:jessie
VOLUME ["/data", "/config"]
EXPOSE 64738/udp
ADD mumble-server.ini /config/mumble-server.ini
ADD start /start

RUN useradd -u 1000 mumble \
&&  chmod 755 /start \
&&  apt-get update \
&&  apt-get install -y --no-install-recommends \
      mumble-server sudo \
&&  rm -rf /var/lib/apt/lists/*

CMD ["/start"]
