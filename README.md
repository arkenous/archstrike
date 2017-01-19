# Docker Image of ArchStrike
[![Build Status](https://travis-ci.org/trileg/archstrike.svg?branch=master)](https://travis-ci.org/trileg/archstrike)
[![](https://images.microbadger.com/badges/image/trileg/archstrike.svg)](http://microbadger.com/images/trileg/archstrike "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/trileg/archstrike.svg)](http://microbadger.com/images/trileg/archstrike "Get your own version badge on microbadger.com")
[![AMA](https://img.shields.io/badge/ask%20me-anything-0e7fc0.svg)](https://github.com/trileg/ama)

This docker image is finished setup ArchStrike base system refer to [Wiki: Setup - ArchStrike](https://archstrike.org/wiki/setup).
This image doesn't install any ArchStrike packages, so you need to install it if you want to use it.

####How to install all packages belong to archstrike group
Run below command if you want to install all packages belong to archstrike group (`pacman -Sg archstrike`).

```
# pacman -Syyu archstrike
```

If you receive below message, type `y` to install ArchStrike packages properly.
- :: gcc-libs-multilib and gcc-libs are in conflict. Remove gcc-libs? [y/N] y
