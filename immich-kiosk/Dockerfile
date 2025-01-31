# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

# Execute during the build of the image
ARG KIOSK_VERSION BUILD_ARCH
RUN \
    wget \
    https://github.com/damongolding/immich-kiosk/releases/download/v${KIOSK_VERSION}/immich-kiosk_Linux_x86_64.tar.gz \
    -O - | tar -xzf - -C /tmp/ && \
    mv /tmp/immich-kiosk /usr/local/bin/

# Copy root filesystem
COPY rootfs /
