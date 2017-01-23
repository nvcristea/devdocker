FROM nginx:1.11-alpine

MAINTAINER Nicolae V. Cristea <coder@cristea.bid>

RUN sed -i -e "s/v3.4/edge/" /etc/apk/repositories && \
    apk update && \
#    apk upgrade && \
    apk add --no-cache nano

COPY nginx.vh.default.conf /etc/nginx/conf.d/default.conf
