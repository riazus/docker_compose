FROM alpine:3.15

ARG DB_PASS ROOT_PASS

LABEL artist=yar_mariadb
LABEL version=0.1

COPY ./conf/* /
RUN apk update && apk upgrade && apk add --no-cache  mariadb mariadb-client sed && \
	mysql_install_db --user=mysql --datadir=/var/db --auth-root-authentication-method=normal && \
	sed -i "s|_WP_PASS|$DB_PASS|g" /init.sql && \
	sed -i "s|_ROOT_PASS|$ROOT_PASS|g" /init.sql  && \
	mkdir /run/mysqld && chown -R mysql:mysql /init.sql /run/mysqld 

CMD sh ./create_db.sh
