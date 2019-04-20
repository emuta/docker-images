FROM golang:alpine

ENV TZ "Asia/Shanghai"

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update \
    && apk add protobuf tzdata curl git wget iproute2 bash upx

CMD ["sh"]