FROM debian:jessie

RUN { \
	set -ex; \
	echo "deb http://deb.torproject.org/torproject.org jessie main" >> /etc/apt/sources.list; \
	apt-key adv --keyserver keys.gnupg.net --recv A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89; \
	apt-get update; \

	apt-get install --no-install-recommends -y tor; \

	rm -rf /var/lib/apt/lists/*; \
}

COPY start_tor /usr/bin/
COPY torrc /etc/tor/

VOLUME /data/tor

ENTRYPOINT ["start_tor"]
