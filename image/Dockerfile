FROM debian:stretch-slim

RUN { set -ex; \
	# install deps
	BUILD_DEPS="gnupg dirmngr"; \
	apt-get update; \
	apt-get install --no-install-recommends -y $BUILD_DEPS; \

	echo "deb http://deb.torproject.org/torproject.org stretch main" >> /etc/apt/sources.list; \
	apt-key adv --keyserver keys.gnupg.net --recv A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89; \
	apt-get update; \

	apt-get install --no-install-recommends -y tor; \

	# clean up
	apt-get purge -y $BUILD_DEPS; \
	apt-get autoremove -y; \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*; \
}

COPY start_tor /usr/bin/
COPY torrc /etc/tor/

VOLUME /data/tor

ENTRYPOINT ["start_tor"]
