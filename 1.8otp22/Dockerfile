FROM erlang:22
ARG VCS_REF
ARG BUILD_DATE

# elixir expects utf8.
ENV ELIXIR_VERSION="v1.8.1" \
  LANG=C.UTF-8

RUN set -xe \
  && ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/archive/${ELIXIR_VERSION}.tar.gz" \
  && ELIXIR_DOWNLOAD_SHA256="de8c636ea999392496ccd9a204ccccbc8cb7f417d948fd12692cda2bd02d9822" \
  && curl -fSL -o elixir-src.tar.gz $ELIXIR_DOWNLOAD_URL \
  && echo "$ELIXIR_DOWNLOAD_SHA256  elixir-src.tar.gz" | sha256sum -c - \
  && mkdir -p /usr/local/src/elixir \
  && tar -xzC /usr/local/src/elixir --strip-components=1 -f elixir-src.tar.gz \
  && rm elixir-src.tar.gz \
  && cd /usr/local/src/elixir \
  && make install clean


LABEL org.label-schema.vcs-ref=$VCS_REF \
          org.label-schema.vcs-url="https://github.com/mloftis/docker-elixir" \
          org.label-schema.build-date=$BUILD_DATE \
          org.label-schema.schema-version="1.0"


RUN set -x && apt-get update && apt-get install -y libgmp-dev libboost-dev postgresql-client ocl-icd-opencl-dev ocl-icd-libopencl1 pocl-opencl-icd

CMD ["iex"]
