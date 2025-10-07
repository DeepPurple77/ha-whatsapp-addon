ARG TARGETARCH
ARG BUILD_ARCH

FROM ghcr.io/home-assistant/$( \
  if [ "$TARGETARCH" = "arm64" ]; then echo "aarch64"; \
  elif [ "$TARGETARCH" = "arm" ]; then echo "armv7"; \
  elif [ "$TARGETARCH" = "386" ]; then echo "i386"; \
  else echo "$TARGETARCH"; fi \
)-base:latest

LABEL maintainer="deeppurple77"
LABEL org.opencontainers.image.source="https://github.com/deeppurple77/ha-whatsapp-addon"

RUN apk add --no-cache git npm

COPY . /
RUN chmod a+x /run.sh
RUN chmod a+x /finish.sh

RUN cd /Baileys && npm i -f && cd .. && npm install -f

EXPOSE 3000
CMD [ "/run.sh" ]
