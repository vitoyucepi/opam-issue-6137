FROM alpine:3.20 as base

ARG OPAM_VERSION
ARG OCAML_VERSION

RUN apk add --no-cache gcc g++ make wget ca-certificates

RUN set -eux; \
      wget -O /usr/local/bin/opam --progress=dot:giga "https://github.com/ocaml/opam/releases/download/$OPAM_VERSION/opam-$OPAM_VERSION-x86_64-linux"; \
      chmod +x /usr/local/bin/opam; \
      opam init --no-setup --disable-sandboxing --compiler ocaml-base-compiler."$OCAML_VERSION";

RUN set -eux; \
      apk add --no-cache bash ffmpeg-dev gmp-dev; \
      opam install --yes prometheus-app ffmpeg;
