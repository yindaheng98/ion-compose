FROM golang:1.16-alpine AS builder
WORKDIR /
RUN apk add git make && \
    git clone https://github.com/yindaheng98/dion && \
    cd dion && make stupid

FROM jrottenberg/ffmpeg:4-alpine
WORKDIR /
COPY --from=builder /dion/stupid /stupid
COPY ./arial.ttf /arial.ttf
COPY ./sfu.toml /sfu.toml
CMD [ "/stupid", "-conf", "/sfu.toml", "-filter", "drawtext=text='%{localtime\:%Y-%M-%d %H.%m.%S}':fontsize=60:x=(w-text_w)/2:y=(h-text_h)/2:fontfile=/arial.ttf" ]