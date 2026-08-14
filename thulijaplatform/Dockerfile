FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl \
    wget \
    git \
    unzip \
    vim \
    nano \
    zip \
    openssh-client \
    tree \
    less \
    ca-certificates \
    openjdk-21-jdk \
    maven \
    default-mysql-client \
    xz-utils \
    && rm -rf /var/lib/apt/lists/*

# s6-overlay
ARG S6_OVERLAY_VERSION=3.2.3.2

ADD https://github.com/just-containers/s6-overlay/releases/download/v${S6_OVERLAY_VERSION}/s6-overlay-noarch.tar.xz /tmp

RUN tar -C / -Jxpf /tmp/s6-overlay-noarch.tar.xz

ADD https://github.com/just-containers/s6-overlay/releases/download/v${S6_OVERLAY_VERSION}/s6-overlay-x86_64.tar.xz /tmp

RUN tar -C / -Jxpf /tmp/s6-overlay-x86_64.tar.xz

# Node.js 22
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# Angular CLI
RUN npm install -g @angular/cli

# s6-overlay service definitions
COPY s6-overlay/angular /etc/s6-overlay/s6-rc.d/angular
COPY s6-overlay/springboot /etc/s6-overlay/s6-rc.d/springboot
COPY s6-overlay/user /etc/s6-overlay/user-bundles.d/user

WORKDIR /workspace/thulijaplatform

ENTRYPOINT ["/init"]
