## -*- docker-image-name: "trileg/archstrike" -*-
FROM trileg/arch-base:latest
MAINTAINER Kensuke Kosaka <k@trileg.net>

COPY patches/pacman.conf.patch.1 /tmp/pacman.conf.patch.1
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.1 && \
  rm -f /tmp/pacman.conf.patch.1 && \
  pacman -Syy &> /dev/null

RUN NEXT_WAIT_TIME=0; until pacman-key --init &> /dev/null && \
  dirmngr < /dev/null &> /dev/null && \
  pacman-key -r 7CBC0D51 &> /dev/null && \
  pacman-key --lsign-key 7CBC0D51 &> /dev/null || [ $NEXT_WAIT_TIME -eq 4 ]; do sleep $(( NEXT_WAIT_TIME++ )); done

RUN pacman -S --noconfirm archstrike-keyring &> /dev/null && \
  pacman -S --noconfirm archstrike-mirrorlist &> /dev/null

COPY patches/pacman.conf.patch.2 /tmp/pacman.conf.patch.2
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.2 && \
  rm -f /tmp/pacman.conf.patch.2 && \
  pacman -Syy &> /dev/null
