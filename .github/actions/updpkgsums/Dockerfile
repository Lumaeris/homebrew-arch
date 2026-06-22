FROM docker.io/library/archlinux:base-devel@sha256:0cf5eb78f8c3ddcdd7ccc3f9168328fb57ec6be0f83f501a0b2006590e0c92ec

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
