## -*- docker-image-name: "k3nsuk3/archstrike" -*-
FROM k3nsuk3/arch-base:latest
MAINTAINER Kensuke Kosaka <k@k3n.link>

RUN pacman -S --noconfirm wget

COPY patches/pacman.conf.patch.1 /tmp/pacman.conf.patch.1
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.1 && \
  rm -f /tmp/pacman.conf.patch.1 && \
  pacman -Syy

RUN NEXT_WAIT_TIME=0; until pacman-key --init 2> /dev/null && \
  dirmngr < /dev/null 2> /dev/null && \
  wget --quiet https://archstrike.org/keyfile.asc && \
  pacman-key --add keyfile.asc 2>/dev/null && \
  pacman-key --lsign-key 9D5F1C051D146843CDA4858BDE64825E7CBC0D51 2> /dev/null || [ $NEXT_WAIT_TIME -eq 4 ]; do sleep $(( NEXT_WAIT_TIME++ )); done && \
  rm -f keyfile.asc

RUN pacman -S --noconfirm archstrike-keyring && \
  pacman -S --noconfirm archstrike-mirrorlist

COPY patches/pacman.conf.patch.2 /tmp/pacman.conf.patch.2
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.2 && \
  rm -f /tmp/pacman.conf.patch.2 && \
  pacman -Syy
