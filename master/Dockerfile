FROM erlang:20
ARG VCS_REF
ARG BUILD_DATE

LABEL org.label-schema.vcs-ref=$VCS_REF \
          org.label-schema.vcs-url="https://github.com/mloftis/docker-elixir" \
          org.label-schema.build-date=$BUILD_DATE \
          org.label-schema.schema-version="1.0"

# elixir expects utf8.
ENV ELIXIR_VERSION="v1.6.0-dev@b53d739" \
	LANG=C.UTF-8

RUN set -xe \
	&& ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/archive/${ELIXIR_VERSION#*@}.tar.gz" \
	&& ELIXIR_DOWNLOAD_SHA256="f407dd16709c2039d9863fc929168aa2c4dd231f3f3cfc81946a2ebdf9a326ef" \
	&& curl -fSL -o elixir-src.tar.gz $ELIXIR_DOWNLOAD_URL \
	&& echo "$ELIXIR_DOWNLOAD_SHA256 elixir-src.tar.gz" | sha256sum -c - \
	&& mkdir -p /usr/src/elixir-src \
	&& tar -xzf elixir-src.tar.gz -C /usr/src/elixir-src --strip-components=1 \
	&& rm elixir-src.tar.gz \
	&& cd /usr/src/elixir-src \
	&& make -j$(nproc) \
	&& make install \
	&& rm -rf /usr/src/elixir-src
RUN apt-get update
RUN apt-get dist-upgrade -y
RUN apt-get -y install libgmp-dev libboost-dev

CMD ["iex"]
