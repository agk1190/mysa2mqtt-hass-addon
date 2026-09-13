# https://developers.home-assistant.io/docs/add-ons/configuration/#add-on-dockerfile
FROM ghcr.io/home-assistant/base:3.24 

# Set mysa2mqtt version
ARG mysa2mqttRevision=3.2.5

# Install requirements for add-on
RUN \
  apk add --no-cache \
    nodejs \
    npm

RUN npm install -g "mysa2mqtt@${mysa2mqttRevision}"

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
