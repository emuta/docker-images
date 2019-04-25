FROM golang:alpine

ENV TZ "Asia/Shanghai"

ENV GRPC_GO_LOG_VERBOSITY_LEVEL "99" 
ENV GRPC_GO_LOG_SEVERITY_LEVEL  "info"

ENV PG_URL       "postgresql://postgres:psqlpass@postgresql:5432/postgres?sslmode=disable"
ENV RABBITMQ_URL "amqp://guest:guest@rabbitmq:5672/"
ENV REDIS_URL    "redis://:@redis:6379/0"

RUN apk update \
    && apk add protobuf tzdata curl git wget iproute2 bash upx \
    && cp /usr/share/zoneinfo/$TZ /etc/localtime \
    && echo $TZ > /etc/timezone \
    && rm -rf /var/cache/apk
    && go get golang.org/x/net/html/charset \
    && go get golang.org/x/crypto/bcrypt \
    && go get github.com/pkg/errors \
    && go get github.com/lib/pq \
    && go get github.com/jinzhu/gorm \
    && go get github.com/jinzhu/gorm/dialects/postgres \
    && go get github.com/go-redis/redis \
    && go get github.com/robfig/cron \
    && go get github.com/gorilla/mux \
    && go get github.com/gorilla/websocket \
    && go get github.com/dgrijalva/jwt-go \
    && go get github.com/sirupsen/logrus \
    && go get github.com/streadway/amqp \
    && go get github.com/satori/go.uuid \
    && go get github.com/robfig/cron \
    && go get google.golang.org/grpc \
    && go get github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway \
    && go get github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger \
    && go get github.com/golang/protobuf/protoc-gen-go \
    && go install github.com/golang/protobuf/protoc-gen-go

CMD ["sh"]