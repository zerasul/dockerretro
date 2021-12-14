FROM ubuntu:latest
RUN apt update
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Madrid
RUN apt install -yq wget curl libarchive13 xz-utils make
RUN apt install -yq gpg pkg-config
RUN wget https://github.com/devkitPro/pacman/releases/download/v1.0.2/devkitpro-pacman.amd64.deb
RUN dpkg -i devkitpro-pacman.amd64.deb
RUN ln -s /proc/self/mounts /etc/mtab
RUN all | dkp-pacman --noconfirm -S nds-dev
ENV DEVKITARM=/opt/devkitpro/devkitARM
ENV DEVKITPRO=/opt/devkitpro
ENV DEVKITPPC=/opt/devkitpro/devkitPPC
RUN mkdir -p /src/nds
WORKDIR /src/nds
VOLUME ["/src/nds"]
CMD ["make"]