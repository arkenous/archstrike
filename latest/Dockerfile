## -*- docker-image-name: "trileg/archstrike" -*-
FROM trileg/arch-base:latest
MAINTAINER Kensuke Kosaka <k@trileg.net>

COPY patches/pacman.conf.patch.1 /tmp/pacman.conf.patch.1
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.1 && rm -f /tmp/pacman.conf.patch.1
RUN pacman -Syy &> /dev/null

RUN pacman-key --init &> /dev/null
RUN dirmngr < /dev/null &> /dev/null
RUN pacman-key -r 7CBC0D51 &> /dev/null
RUN pacman-key --lsign-key 7CBC0D51 &> /dev/null

RUN pacman -S --noconfirm archstrike-keyring &> /dev/null
RUN pacman -S --noconfirm archstrike-mirrorlist &> /dev/null

COPY patches/pacman.conf.patch.2 /tmp/pacman.conf.patch.2
RUN patch -u /etc/pacman.conf < /tmp/pacman.conf.patch.2 && rm -f /tmp/pacman.conf.patch.2
RUN pacman -Syy &> /dev/null
