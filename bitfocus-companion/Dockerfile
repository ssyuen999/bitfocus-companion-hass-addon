ARG BUILD_ARCH=aarch64

# Selecteer de juiste image op basis van de architectuur linux/arm64=aarch64_image linux/amd64=amd64_image
# linux/arm64
FROM ghcr.io/bitfocus/companion/companion:4.3.2-9226-stable-1b1835a3e2@sha256:7f4fdbed18fda2dc33b80b685ac297c11a128c2512b6b971d75d0e59b22f1de2 AS aarch64_image
# linux/amd64
FROM ghcr.io/bitfocus/companion/companion:4.3.2-9226-stable-1b1835a3e2@sha256:4b3b24aa955cd58dfbbf3a7ea43b7bd59fc1fb3eaf9f5103bed282c828e6e8cd AS amd64_image
# De eigenlijke image die wordt gebruikt
FROM ${BUILD_ARCH}_image

USER root

# Kopieer het startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Verander het entrypoint
ENTRYPOINT ["/run_companion.sh"]
