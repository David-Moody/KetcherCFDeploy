FROM alpine:latest AS base
ARG KETCHER_VERSION=3.4.0

RUN apk --no-cache add zip
ADD https://github.com/epam/ketcher/releases/download/v$KETCHER_VERSION/ketcher-standalone-$KETCHER_VERSION.zip /download/
RUN unzip /download/ketcher-standalone-$KETCHER_VERSION.zip -d /decompressed/

FROM nginx:alpine-slim AS final

COPY --from=base /decompressed/standalone/ /usr/share/nginx/html
