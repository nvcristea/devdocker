FROM alpine:3.4

MAINTAINER Nicolae V. Cristea <coder@cristea.bid>

RUN apk upgrade && \
    apk add --update --no-cache \
        curl \
        nano \
        git && \
    rm -rf /var/cache/apk/*

CMD ["sh"]
