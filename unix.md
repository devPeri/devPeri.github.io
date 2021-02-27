---
layout: page
title: UNIX
navigation: 11
---

UNIX
----

### VIM
- [Is Vim Really Not For You? A Beginner Guide](https://thevaluable.dev/vim-beginner/)
- [A Vim Guide for Intermediate Users](https://thevaluable.dev/vim-intermediate/)
- [A Vim Guide for Advanced Users](https://thevaluable.dev/vim-advanced/)

### Linux
#### chroot
Pre:
```shell
cd CHROOTDIR
mount --bind /dev dev
mount --bind /proc proc
mount --bind /sys sys
```

Post:
```shell
umount dev
umount proc
umount sys
```

### Debian
Purge left-over configuration files of uninstalled packages:
```shell
dpkg -l | grep ^rc | awk '{print($2)}' 
```
