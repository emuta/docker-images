FROM golang:alpine

ENV TZ "Asia/Shanghai"

ENV GRPC_GO_LOG_VERBOSITY_LEVEL "99" 
ENV GRPC_GO_LOG_SEVERITY_LEVEL  "info"

go env -w GO111MODULE=on
go env -w GOPROXY="https://goproxy.io,direct"

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update \
    && apk add protobuf tzdata curl git wget iproute2 bash upx \
    && cp /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone

CMD ["sh"]