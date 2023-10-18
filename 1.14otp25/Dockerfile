FROM erlang:25

# elixir expects utf8.
ENV ELIXIR_VERSION="v1.14.5" \
	LANG=C.UTF-8

RUN set -xe \
	&& ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/archive/${ELIXIR_VERSION}.tar.gz" \
	&& ELIXIR_DOWNLOAD_SHA256="2ea249566c67e57f8365ecdcd0efd9b6c375f57609b3ac2de326488ac37c8ebd" \
	&& curl -fSL -o elixir-src.tar.gz $ELIXIR_DOWNLOAD_URL \
	&& echo "$ELIXIR_DOWNLOAD_SHA256  elixir-src.tar.gz" | sha256sum -c - \
	&& mkdir -p /usr/local/src/elixir \
	&& tar -xzC /usr/local/src/elixir --strip-components=1 -f elixir-src.tar.gz \
	&& rm elixir-src.tar.gz \
	&& cd /usr/local/src/elixir \
	&& make install clean \
	&& find /usr/local/src/elixir/ -type f -not -regex "/usr/local/src/elixir/lib/[^\/]*/lib.*" -exec rm -rf {} + \
	&& find /usr/local/src/elixir/ -type d -depth -empty -delete

RUN set -x && apt-get update && apt-get install -y libgmp-dev libboost-dev postgresql-client ocl-icd-opencl-dev ocl-icd-libopencl1 pocl-opencl-icd && \
    rm -rf /var/lib/apt/lists/*

CMD ["iex"]
