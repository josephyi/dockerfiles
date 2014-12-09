FROM josephyi/elixir:latest

MAINTAINER Joseph Yi <joe@josephyi.com>

RUN apt-get install git -y

WORKDIR /
RUN git clone https://github.com/phoenixframework/phoenix.git
WORKDIR /phoenix
RUN git checkout v0.6.2
RUN mix do local.hex --force, local.rebar, deps.get, compile

EXPOSE 4000

VOLUME ["/app"]
WORKDIR /app