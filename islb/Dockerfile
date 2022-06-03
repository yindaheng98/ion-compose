FROM golang:1.18-alpine AS builder
WORKDIR /
RUN apk add git make && \
    git clone https://github.com/yindaheng98/dion
RUN cd /dion && make islb

FROM alpine
WORKDIR /
COPY --from=builder /dion/islb /islb
COPY ./islb.toml /islb.toml
ENTRYPOINT [ "/islb" ]
CMD [ "-c", "/islb.toml" ]