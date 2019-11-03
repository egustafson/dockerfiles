FROM alpine:latest

RUN apk --no-cache update \
    && apk add --no-cache --update \
    rsyslog \
    rsyslog-relp \
    rsyslog-mmutf8fix \
    rsyslog-mmjsonparse

RUN mkdir /config /logs
VOLUME [ "/config", "/logs", "/var/run/syslog/dev" ]
EXPOSE 2514/tcp 514/tcp 514/udp

ENTRYPOINT ["rsyslogd", "-n", "-f", "/config/rsyslog.conf"]
