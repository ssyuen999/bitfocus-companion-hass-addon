ARG BUILD_ARCH=aarch64

# Selecteer de juiste image op basis van de architectuur linux/arm64=aarch64_image linux/amd64=amd64_image
FROM ghcr.io/bitfocus/companion/companion:4.2.3-8775-stable-9badd326db@sha256:902ca4460fc29bb214cdc7c8794bcde144056a3ba24d7845a901785a3a29981c AS aarch64_image
FROM ghcr.io/bitfocus/companion/companion:4.2.3-8775-stable-9badd326db@sha256:57f267cb2377fcb953339a83c47cf48bff922121a11213f56569ea63f67714ba AS amd64_image

# De eigenlijke image die wordt gebruikt
FROM ${BUILD_ARCH}_image

USER root

# Kopieer het startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Verander het entrypoint
ENTRYPOINT ["/run_companion.sh"]
