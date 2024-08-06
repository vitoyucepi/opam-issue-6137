FROM alpine:3.20

ARG OCAML_VERSION

RUN apk add --no-cache alpine-sdk wget ca-certificates opam

RUN opam init --no-setup --disable-sandboxing --compiler ocaml-base-compiler."$OCAML_VERSION";

RUN set -eux; \
      apk add ffmpeg-dev bash gmp-dev; \
      opam install --yes prometheus-app ffmpeg;
