FROM ubuntu:24.04

ARG OCAML_VERSION

RUN set -eux; \
      apt-get update; \
      apt-get install --no-install-recommends -y \
        gcc \
        g++ \
        make \
        patch \
        unzip \
        bzip2 \
        wget \
        ca-certificates \
        opam \
      ;

RUN opam init --no-setup --disable-sandboxing --compiler ocaml-base-compiler."$OCAML_VERSION";

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
