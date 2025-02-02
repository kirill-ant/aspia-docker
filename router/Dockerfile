FROM debian:bookworm

LABEL maintainer="kirill_ant"
LABEL image_version="0.0.1"
LABEL org.opencontainers.image.title="aspia-router container"
LABEL org.opencontainers.image.version="0.0.1"

ENV ASPIA_LOG_TO_STDOUT=1
ENV ASPIA_LOG_LEVEL=0

VOLUME ["/etc/aspia", "/var/lib/aspia"]

ADD https://github.com/dchapyshev/aspia/releases/download/v2.7.0/aspia-router-2.7.0-x86_64.deb /tmp/
RUN apt-get update && \
    dpkg -i /tmp/aspia-router-2.7.0-x86_64.deb \
    && rm /tmp/aspia-router-2.7.0-x86_64.deb

WORKDIR /usr/bin

ENTRYPOINT ["aspia_router"]