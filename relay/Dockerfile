FROM debian:bookworm-slim

LABEL maintainer="kirill_ant"
LABEL image_version="0.0.1"
LABEL org.opencontainers.image.title="aspia-relay container"
LABEL org.opencontainers.image.version="0.0.1"

ENV ASPIA_LOG_TO_STDOUT=1
ENV ASPIA_LOG_LEVEL=0

VOLUME ["/etc/aspia"]

ADD https://github.com/dchapyshev/aspia/releases/download/v2.7.0/aspia-relay-2.7.0-x86_64.deb /tmp/
RUN apt-get update && \
    dpkg -i /tmp/aspia-relay-2.7.0-x86_64.deb \
    && rm /tmp/aspia-relay-2.7.0-x86_64.deb

WORKDIR /usr/bin

ENTRYPOINT ["aspia_relay"]