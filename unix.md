---
layout: page
title: UNIX
navigation: 11
---

UNIX
====

### VIM
- [Is Vim Really Not For You? A Beginner Guide](https://thevaluable.dev/vim-beginner/)
- [A Vim Guide for Intermediate Users](https://thevaluable.dev/vim-intermediate/)
- [A Vim Guide for Advanced Users](https://thevaluable.dev/vim-advanced/)

### Linux
#### chroot
Pre:
```console
cd CHROOTDIR
mount --bind /dev dev
mount --bind /proc proc
mount --bind /sys sys
```

Post:
```console
umount dev
umount proc
umount sys
```

#### ext4
Journal:
```console
# ENABLE
tune2fs -O ^has_journal DEVICE

# DISABLE
tune2fs -o discard DEVICE

dumpe2fs DEVICE | grep journal
```

Enable writeback mode (this mode will typically provide the best ext4 performance):
```console
tune2fs -o journal_data_writeback DEVIE
```

For higher performance add fstab opions: data=writeback,noatime,nodiratime i.e:
```
/dev/sdXY /DIR ext4 defaults,data=writeback,noatime,nodiratime 0 0
```

### Debian
Purge left-over configuration files of uninstalled packages:
```console
dpkg -l | grep ^rc | awk '{print($2)}' | xargs apt-get -y purge
```
