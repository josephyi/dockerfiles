FROM debian:jessie

MAINTAINER Joseph Yi <joe@josephyi.com>

RUN apt-get update && apt-get install -y \
  
WORKDIR /tmp
RUN wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
RUN dpkg -i erlang-solutions_1.0_all.deb
RUN apt-get update && apt-get install -y \
  erlang \
  erlang-base-hipe
RUN apt-get clean

ENTRYPOINT ['erl']