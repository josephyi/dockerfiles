FROM msaraiva/elixir-dev:latest

MAINTAINER Joseph Yi <joe@josephyi.com>

# Borrowed node install from smebberson/alpine-nodejs
ENV NODE_VERSION=v5.5.0 NPM_VERSION=3
RUN apk add --update git curl make gcc g++ python linux-headers libgcc libstdc++ binutils-gold && \
    curl -sSL https://nodejs.org/dist/${NODE_VERSION}/node-${NODE_VERSION}.tar.gz | tar -xz && \
    cd /node-${NODE_VERSION} && \
    ./configure --prefix=/usr --without-snapshot --fully-static && \
    make -j$(grep -c ^processor /proc/cpuinfo 2>/dev/null || 1) && \
    make install && \
    cd / && \
    npm install -g npm@${NPM_VERSION} && \
    apk del gcc g++ linux-headers libgcc libstdc++ binutils-gold && \
    rm -rf /etc/ssl /node-${NODE_VERSION} /usr/include \
    /usr/share/man /tmp/* /var/cache/apk/* /root/.npm /root/.node-gyp \
    /usr/lib/node_modules/npm/man /usr/lib/node_modules/npm/doc /usr/lib/node_modules/npm/html

WORKDIR /
#RUN mix do local.hex local.rebar, deps.get, compile

RUN mix archive.install https://github.com/phoenixframework/archives/raw/master/phoenix_new.ez --force

EXPOSE 4000

VOLUME ["/app"]
WORKDIR /app
