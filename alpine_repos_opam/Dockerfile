FROM alpine:3.20

ARG OCAML_VERSION

RUN apk add --no-cache gcc g++ make opam

RUN set -eux; \
      opam init --no-setup --disable-sandboxing --compiler ocaml-base-compiler."$OCAML_VERSION";

RUN set -eux; \
      apk add --no-cache pkgconf bash ffmpeg-dev gmp-dev; \
      opam install --yes prometheus-app ffmpeg;
