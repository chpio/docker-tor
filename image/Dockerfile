FROM alpine:latest

RUN \
	apk add tor \
		--update \
		--update-cache \
		--repository http://dl-3.alpinelinux.org/alpine/edge/testing/ \
	&& rm -rf /var/cache/apk/*

ADD ./fs /
RUN chown -R tor /etc/tor

CMD ["start_tor"]
