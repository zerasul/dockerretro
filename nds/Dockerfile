FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Madrid

RUN apt update && \
  apt install -yq wget curl libarchive13 xz-utils make gpg pkg-config && \
  wget https://github.com/devkitPro/pacman/releases/download/v1.0.2/devkitpro-pacman.amd64.deb && \
  dpkg -i devkitpro-pacman.amd64.deb && \
  ln -s /proc/self/mounts /etc/mtab && \
  all | dkp-pacman --noconfirm -S nds-dev && \
  mkdir -p /src/nds

ENV DEVKITARM=/opt/devkitpro/devkitARM
ENV DEVKITPRO=/opt/devkitpro
ENV DEVKITPPC=/opt/devkitpro/devkitPPC
ENV PATH="${DEVKITPRO}/tools/bin:${PATH}"
WORKDIR /src/nds
VOLUME ["/src/nds"]
CMD ["make"]