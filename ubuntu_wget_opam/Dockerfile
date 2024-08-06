FROM ubuntu:24.04

ARG OPAM_VERSION
ARG OCAML_VERSION

RUN set -eux; \
      apt-get update; \
      apt-get install --no-install-recommends -y \
        gcc \
        g++ \
        make \
        patch \
        unzip \
        wget \
        bzip2 \
        ca-certificates \
      ;

RUN set -eux; \
      wget -O /usr/local/bin/opam --progress=dot:giga "https://github.com/ocaml/opam/releases/download/$OPAM_VERSION/opam-$OPAM_VERSION-x86_64-linux"; \
      chmod +x /usr/local/bin/opam; \
      opam init --no-setup --disable-sandboxing --compiler ocaml-base-compiler."$OCAML_VERSION";

RUN set -eux; \
      apt-get update; \
      apt-get install --no-install-recommends -y \
        libavcodec-dev \
        libavdevice-dev \
        libavfilter-dev \
        libavformat-dev \
        libavutil-dev \
        libswresample-dev \
        libswscale-dev \
        pkg-config \
        libgmp-dev \
      ; \
      opam install --yes prometheus-app ffmpeg;
