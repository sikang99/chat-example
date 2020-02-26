FROM cojam/golang:1.13.8.0-alpine-3.10
MAINTAINER "Stoney Kang <sikang99@gmail.com>"
##==========================================================================
ENV GO111MODULE=on
ENV CGO_ENABLED=0
RUN mkdir /app
ADD src/ /app/
RUN cd /app \
    && go build -o niltalk *.go \
    && rm -f *.go
##--------------------------------------------------------------------------
WORKDIR /app
##==========================================================================
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
##==========================================================================






