ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:latest
FROM ${BUILD_FROM}

LABEL maintainer="deeppurple77"
LABEL org.opencontainers.image.source="https://github.com/deeppurple77/ha-whatsapp-addon"

RUN apk add --no-cache git npm

COPY . /
RUN chmod a+x /run.sh
RUN chmod a+x /finish.sh

RUN cd /Baileys && npm --verbose i -f && cd .. && npm --verbose install -f

EXPOSE 3000
CMD [ "/run.sh" ]
