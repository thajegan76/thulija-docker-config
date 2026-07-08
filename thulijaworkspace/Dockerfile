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
    sqlite3 \
    php \
    php-cli \
    php-mysql \
    php-xml \
    php-mbstring \
    php-curl \
    php-zip \
    php-sqlite3 \
    php-bcmath \
    php-intl \
    default-mysql-client \
    && rm -rf /var/lib/apt/lists/*

# Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Node.js 22
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# Angular CLI and Ionic CLI
RUN npm install -g @angular/cli @ionic/cli

WORKDIR /workspace/thulijaworkspace

CMD ["bash"]