FROM ubuntu:latest

ENV PATH /opt/local/go/bin:$PATH
ENV PATH /work/bin:/opt/local/go/bin:$PATH
ENV GOROOT /opt/local/go
ENV GOPATH /work

RUN apt-get update && \
    apt-get install -y unzip curl git build-essential && \
    apt-get clean && \
    rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*
    curl -LO https://storage.googleapis.com/golang/go1.4.linux-amd64.tar.gz && \
    tar xzf go1.4.linux-amd64.tar.gz && \
    mkdir -p /opt/local && \
    mv go /opt/local/ && \
    go get -u github.com/laher/goxc && \
    curl -LO https://github.com/tcnksm/ghr/releases/download/v0.2.0/ghr_v0.2.0_linux_amd64.zip && \
    unzip ghr_v0.2.0_linux_amd64.zip && \
    mv ghr /usr/local/bin && \
    rm -rf ghr_v0.2.0_linux_amd64.zip

CMD echo "goxc docker built for go version 1.4"