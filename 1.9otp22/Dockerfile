FROM erlang:22
ARG VCS_REF
ARG BUILD_DATE

# elixir expects utf8.
ENV ELIXIR_VERSION="v1.9.0" \
  LANG=C.UTF-8

RUN set -xe \
  && ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/archive/${ELIXIR_VERSION}.tar.gz" \
  && ELIXIR_DOWNLOAD_SHA256="dbf4cb66634e22d60fe4aa162946c992257f700c7db123212e7e29d1c0b0c487" \
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
