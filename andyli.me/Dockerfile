FROM debian:jessie

RUN apt-get update && apt-get install --no-install-recommends -y ca-certificates git-core
RUN git clone https://github.com/andyidea/andyli.me.git /src
RUN git submodule update --init --recursive /src
VOLUME ["/src"]
WORKDIR /src
ENTRYPOINT ["git"]
CMD ["pull"]
