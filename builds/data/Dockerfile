FROM alpine:3.4
COPY confs /tmp/confs
ARG CONF_DIR=/tmp/confs

RUN set -x \
        && cd $CONF_DIR \
        && mkdir -p -m 755 /usr/share/elasticsearch/data \
        && cp -rf elasticsearch /usr/share/elasticsearch/config \
        && mkdir -p -m 755 /var/lib/mysql \
        && mkdir -p -m 755 /etc/mysql/conf.d \
        && cp mysql/default.cnf /etc/mysql/conf.d/default.cnf \
        && mkdir -p -m 755 /etc/nginx \
        && cp -rf nginx/conf.d /etc/nginx/conf.d \
        && mkdir -p -m 755 /etc/redis \
        && cp -rf redis/redis.conf /etc/redis/redis.conf

VOLUME ["/var/lib/mysql", "/etc/mysql/conf.d", "/etc/nginx/conf.d", "/etc/redis", "/usr/share/elasticsearch/data", "/usr/share/elasticsearch/config"]

CMD ["sh"]
