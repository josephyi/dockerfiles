FROM josephyi/erlang:latest

MAINTAINER Joseph Yi <joe@josephyi.com>

RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

RUN apt-get install -y \
  elixir
  
CMD ["iex"]