ARG ALPINE_VERSION=latest
FROM alpine:${ALPINE_VERSION}

MAINTAINER David Feldman <dbfeldman@gmail.com>

COPY rootfs /

RUN apk-install erlang && clear-apk-cache

ARG ELIXIR_VERSION=1.5.1

RUN apk-install --virtual deps wget ca-certificates && \
    wget https://github.com/elixir-lang/elixir/releases/download/v${ELIXIR_VERSION}/Precompiled.zip && \
    mkdir -p /opt/elixir-${ELIXIR_VERSION}/ && \
    unzip Precompiled.zip -d /opt/elixir-${ELIXIR_VERSION}/ && \
    rm Precompiled.zip && \
    apk del deps && \
    rm -rf /etc/ssl && \
    clear-apk-cache

ENV ELIXIR_VERSION=$ELIXIR_VERSION \
    PATH=$PATH:/opt/elixir-${ELIXIR_VERSION}/bin
