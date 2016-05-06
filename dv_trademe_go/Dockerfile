FROM golang:1.6.2
MAINTAINER Danie Viljoen <davilj@gmail.com>
RUN mkdir -p src/github.com/davilj/trademe
RUN git clone  https://github.com/davilj/go-trademe.git src/github.com/davilj/trademe
RUN cd src
RUN go get github.com/davilj/trademe
RUN go install github.com/davilj/trademe

VOLUME  ["/trademeData"]

ENTRYPOINT ["trademe"]
