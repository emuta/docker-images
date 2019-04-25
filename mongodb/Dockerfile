FROM alpine

ENV TZ       "Asia/Shanghai"
ENV DBPATH   "/data/db"
ENV PACKAGES "tzdata mongodb mongodb-tools"

RUN apk update \
    && apk add $PACKAGES --no-cache \
    && cp /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone \
    && rm -rf /var/cache/apk

RUN makdir -p $DBPATH \
    && chown -R mongodb $DBPATH

CMD ["mongod", "--dbpath", "$DBPATH"]