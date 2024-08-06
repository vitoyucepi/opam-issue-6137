ARG OCAML_VERSION

FROM ocaml/opam:ubuntu-24.04-ocaml-${OCAML_VERSION}

RUN set -eux; \
      sudo ln -f /usr/bin/opam-2.2 /usr/bin/opam; \
      opam init --reinit -n

RUN set -eux; \
      sudo apt-get update; \
      sudo apt-get install --no-install-recommends -y \
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