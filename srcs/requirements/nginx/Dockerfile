FROM alpine:3.15

LABEL artist=yar_nginx
LABEL version=0.1

RUN apk update && apk upgrade && apk add --no-cache  nginx curl

COPY ./conf/nginx.conf /etc/nginx/http.d/nginx.conf
COPY ./tools/* /etc/nginx/ssl/

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]

