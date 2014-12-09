FROM josephyi/elixir:latest

MAINTAINER Joseph Yi <joe@josephyi.com>

RUN apt-get install git -y

WORKDIR /tmp
RUN git clone https://github.com/phoenixframework/phoenix.git
WORKDIR /tmp/phoenix
RUN git checkout v0.6.2
RUN mix do local.hex --force, local.rebar, deps.get, compile
  
VOLUME ["/phoenix"]
WORKDIR /phoenix