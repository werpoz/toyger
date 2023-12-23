# syntax=docker/dockerfile:1

ARG NODE_VERSION=20.5.0

FROM node:$NODE_VERSION-alpine3.18 AS base

LABEL com.doulog.maintainer='Duolog development team <abel.seminario.leon@duolog.com>'

ARG USER_ID=0
ARG GROUP_ID=0

RUN \
    if [ ${USER_ID} -ne 0 ] && [ ${GROUP_ID} -ne 0 ]; then \
    adduser -D -H ${USER_ID} ${GROUP_ID}; \
    fi \
    && apk add --no-cache \
    git~=2 \
    # CVE https://www.cve.org/CVERecord?id=CVE-2023-5363.
    libcrypto3~=3.1.4 \
    libssl3~=3.1.4
