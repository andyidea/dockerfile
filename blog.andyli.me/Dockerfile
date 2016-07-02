FROM debian:jessie

RUN apt-get update && apt-get install --no-install-recommends -y \
    ca-certificates \
    curl \
    mercurial \
    git-core

RUN curl -s https://storage.googleapis.com/golang/go1.6.linux-amd64.tar.gz | tar -v -C /usr/local -xz

ENV GOPATH /go
ENV GOROOT /usr/local/go
ENV PATH $PATH:/usr/local/go/bin:/go/bin

RUN apt-get update && apt-get install --no-install-recommends -y bzr

RUN go get github.com/spf13/hugo

RUN git clone https://github.com/andyidea/blog.andyli.me.git /blog

RUN cd /blog && git submodule update --init --recursive

WORKDIR /blog

VOLUME ["/var/www/blog"]

CMD ["sh", "run.sh"]