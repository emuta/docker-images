FROM alpine

ENV TZ "Asia/Shanghai"

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update \
    && apk add python2 python-dev libgcc g++ protobuf cython-dev \
    && python -m ensurepip \
    && pip install cython protobuf grpcio grpcio-tools

CMD ["python"]