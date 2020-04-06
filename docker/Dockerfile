# copy from https://github.com/teddysun/across/blob/master/docker/l2tp/Dockerfile

FROM alpine:edge

RUN apk add -U ca-certificates openssl libreswan xl2tpd \
	&& ipsec initnss \
	&& rm -rf /var/cache/apk/*

COPY ipsec /etc/init.d/ipsec
COPY l2tp.sh /usr/bin/l2tp
COPY l2tpctl.sh /usr/bin/l2tpctl
RUN chmod 755 /etc/init.d/ipsec /usr/bin/l2tp /usr/bin/l2tpctl

VOLUME /lib/modules
VOLUME /config

EXPOSE 500/udp 4500/udp

CMD [ "l2tp" ]
