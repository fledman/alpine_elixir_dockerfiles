ARG ALPINE_ERLANG_VERSION=latest

FROM alpine-erlang:$ALPINE_ERLANG_VERSION

MAINTAINER David Feldman <dbfeldman@gmail.com>

ARG ELIXIR_VERSION=1.5.1
ENV ELIXIR_VERSION $ELIXIR_VERSION

RUN apk-install --virtual deps wget ca-certificates && \
    wget https://github.com/elixir-lang/elixir/releases/download/v${ELIXIR_VERSION}/Precompiled.zip && \
    mkdir -p /opt/elixir-${ELIXIR_VERSION}/ && \
    unzip Precompiled.zip -d /opt/elixir-${ELIXIR_VERSION}/ && \
    rm Precompiled.zip && \
    apk del deps && \
    rm -rf /etc/ssl && \
    clear-apk-cache

ENV PATH $PATH:/opt/elixir-${ELIXIR_VERSION}/bin
