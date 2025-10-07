# Use the multi-arch Home Assistant add-on base image
FROM ghcr.io/hassio-addons/base:stable

LABEL maintainer="deeppurple77"
LABEL org.opencontainers.image.source="https://github.com/deeppurple77/ha-whatsapp-addon"

RUN apk add --no-cache git npm

COPY . /
RUN chmod a+x /run.sh
RUN chmod a+x /finish.sh

RUN cd /Baileys && npm i -f && cd .. && npm install -f && npm cache clean --force

EXPOSE 3000
CMD [ "/run.sh" ]
