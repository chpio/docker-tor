FROM alpine:3.3

RUN \
	apk add tor \
		--update \
		--update-cache \
		--repository http://dl-3.alpinelinux.org/alpine/edge/testing/ \
	&& rm -rf /var/cache/apk/*

COPY start_tor /usr/bin/
COPY torrc /opt/

VOLUME /data/tor

CMD ["start_tor"]
