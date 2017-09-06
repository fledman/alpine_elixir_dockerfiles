ARG ALPINE_ELIXIR_VERSION=latest

FROM alpine-elixir:$ALPINE_ELIXIR_VERSION

MAINTAINER David Feldman <dbfeldman@gmail.com>

RUN apk-install erlang-crypto \
                erlang-syntax-tools \
                erlang-parsetools \
                erlang-inets \
                erlang-ssl \
                erlang-public-key \
                erlang-eunit \
                erlang-asn1 \
                erlang-sasl \
                erlang-erl-interface \
                erlang-dev && \
    clear-apk-cache
