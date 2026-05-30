ARG BUILD_ARCH=aarch64

# Selecteer de juiste image op basis van de architectuur linux/arm64=aarch64_image linux/amd64=amd64_image
# linux/arm64
FROM ghcr.io/bitfocus/companion/companion:4.3.3-9230-stable-06a7406709@sha256:072ff3de43b26cc5ee31861dea81caa16a2b9ed35ffd9f587a2b85d2f816847b AS aarch64_image
# linux/amd64
FROM ghcr.io/bitfocus/companion/companion:4.3.3-9230-stable-06a7406709@sha256:1f228fbdeda159d4004affaf8e6e4f94dfe7b133c7224e4f2c468da94ffd0793 AS amd64_image
# De eigenlijke image die wordt gebruikt
FROM ${BUILD_ARCH}_image

USER root

# Kopieer het startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Verander het entrypoint
ENTRYPOINT ["/run_companion.sh"]
