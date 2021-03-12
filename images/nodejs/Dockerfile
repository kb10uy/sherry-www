LABEL maintainer="kb10uy"

FROM jrottenberg/ffmpeg:4.3-alpine AS ffmpeg

FROM node:alpine3.13
COPY --from=ffmpeg /usr/local /usr/local
