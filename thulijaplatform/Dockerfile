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
    && rm -rf /var/lib/apt/lists/*

# Node.js 22
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# Angular CLI
RUN npm install -g @angular/cli

WORKDIR /workspace/thulijaplatform

CMD ["bash"]