FROM alpine:latest

RUN apk add tor \
	--update \
	--update-cache \
	--repository http://dl-3.alpinelinux.org/alpine/edge/testing/

ADD ./fs /
RUN chown -R tor /etc/tor

CMD ["start_tor"]
