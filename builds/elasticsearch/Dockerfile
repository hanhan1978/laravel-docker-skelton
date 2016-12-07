FROM elasticsearch:2.3

ARG CONF_PATH=/tmp/elasticsearch_conf

COPY config $CONF_PATH

RUN set -x \
  && mkdir -p -m 755 /usr/local/sbin \
  && rm -rf /usr/share/elasticsearch/config \
  && cp -rf $CONF_PATH /usr/share/elasticsearch/config \
  && chown -R elasticsearch:elasticsearch /usr/share/elasticsearch/config \
  && rm -rf $CONF_PATH \
  && plugin install analysis-kuromoji \
  && plugin install mobz/elasticsearch-head

EXPOSE 9200 9300

CMD ["elasticsearch"]
