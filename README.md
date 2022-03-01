# Wrapfs

[wrapfs website](https://wrapfs.filesystems.org/)

It seems that the Wrapfs is out of maintenance since 2019 and the Wrapfs mailing list cannot be visited. 

This project adapts Wrapfs for new Linux kernel version. Any PR/Issue is welcome.

## test

| Version   | 5.6  | 5.7  | 5.8  | 5.9  | 5.10 | 5.11 | 5.12 | 5.13 | 5.14 | 5.15 |
| --------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| `mount`   |      |      |      |      |      | y    |      | y    |      |      |
| `mkdir`   |      |      |      |      |      | y    |      | y    |      |      |
| `touch`   |      |      |      |      |      | y    |      | y    |      |      |
| `mv`      |      |      |      |      |      | y    |      | y    |      |      |
| `cat`     |      |      |      |      |      | y    |      | y    |      |      |
| `echo >>` |      |      |      |      |      | y    |      | y    |      |      |
| `ln`      |      |      |      |      |      | y    |      | y    |      |      |
| `ln -s`   |      |      |      |      |      | y    |      | y    |      |      |
| `chmod`   |      |      |      |      |      | y    |      | y    |      |      |
| `chown`   |      |      |      |      |      | y    |      | y    |      |      |
| `rm`      |      |      |      |      |      | y    |      | y    |      |      |
| `rmdir`   |      |      |      |      |      | y    |      | y    |      |      |
| `execve`  |      |      |      |      |      | y    |      | y    |      |      |
| `umount`  |      |      |      |      |      | y    |      | y    |      |      |

## build

Linux distributions provide the commands `modprobe `, `insmod `and `depmod `within a package.

VERSION is your linux kernel version. you can see that use `uname -r`

```
sudo apt-get install build-essential kmod linux-headers-VERSION
```

Then choose the corresponding folder and make

```sh
cd 5.11
make
```

Or if you have source code of some version of linux, you can make in it.

## usage

After you build the kernel module, then you can use it.

```sh
# install module
insmod wrapfs.ko
# mount dir
mount -t wrapfs /some/dir /some/dir
# umount dir
umount /some/dir
# uninstall module
rmmod wrapfs.ko
```

