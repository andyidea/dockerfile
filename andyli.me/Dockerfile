FROM debian:jessie

RUN apt-get update && apt-get install --no-install-recommends -y ca-certificates git-core
RUN git clone https://github.com/andyidea/andyli.me.git /src
RUN cd /src && git submodule update --init --recursive
VOLUME ["/src"]
WORKDIR /src
COPY run.sh /
CMD ["sh", "run.sh"]
