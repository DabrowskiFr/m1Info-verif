FROM ubuntu:22.04

MAINTAINER Frédéric DABROWSKI

RUN	apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y \
		autoconf \
		pkg-config \
		python3 \
		libgmp10 \
		libgmp-dev \
		libgtksourceview-3.0-1 \
		libgtksourceview-3.0-dev \
		opam
RUN chmod u+s /usr/bin/bwrap
RUN	opam init --disable-sandboxing && \
	eval $(opam env --switch=default) && \
	opam --yes install alt-ergo.2.4.1 why3-ide.1.5.1
RUN     eval $(opam env)
ENV     PATH="${PATH}:/root/.opam/default/bin"
RUN	why3 config detect
RUN	apt-get autoremove -y \
		autoconf \
		pkg-config \
		python3 \
		libgmp-dev \
		libgtksourceview-3.0-dev \
		opam && \
	rm -rf /var/lib/apt/lists/* 
WORKDIR /root/why3
