FROM postgres:11.0

ENV PLV8_VERSION=2.3.8

RUN set -x && \
  apt update && \
  apt upgrade -y && \
  apt install -y \
    git make g++ python wget postgresql-server-dev-11 libc++-dev pkg-config

RUN set -x && \
  wget https://github.com/plv8/plv8/archive/v$PLV8_VERSION.tar.gz && \
  tar zxvf v$PLV8_VERSION.tar.gz && \
  cd plv8-$PLV8_VERSION && \
  make install && \
  apt purge -y make g++ python wget postgresql-server-dev-11 libc++-dev pkg-config && \
  apt purge -y --auto-remove && \
  apt clean && \
  rm -rf /var/lib/apt/lists/*
