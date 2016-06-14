# Docker Image of ArchStrike
[![Build Status](https://travis-ci.org/trileg/archstrike.svg?branch=master)](https://travis-ci.org/trileg/archstrike)
[![Docker Stars](https://img.shields.io/docker/stars/trileg/archstrike.svg?maxAge=3600)](https://hub.docker.com/r/trileg/archstrike/)
[![Docker Pulls](https://img.shields.io/docker/pulls/trileg/archstrike.svg?maxAge=3600)](https://hub.docker.com/r/trileg/archstrike/)
[![AMA](https://img.shields.io/badge/ask%20me-anything-0e7fc0.svg)](https://github.com/trileg/ama)
[![GitHub release](https://img.shields.io/github/release/trileg/archstrike.svg?maxAge=86400)](https://github.com/trileg/archstrike/releases/latest)

This docker image is finished setup ArchStrike base system refer to [Wiki: Setup - ArchStrike](https://archstrike.org/wiki/setup).
This image doesn't install any ArchStrike packages, so you need to install it if you want to use it.

####How to install all packages belong to archstrike group
Run below command if you want to install all packages belong to archstrike group (`pacman -Sg archstrike`).

```
# pacman -Syyu archstrike
```

If you receive below message, type `y` to install ArchStrike packages properly.
- :: gcc-libs-multilib and gcc-libs are in conflict. Remove gcc-libs? [y/N] y
