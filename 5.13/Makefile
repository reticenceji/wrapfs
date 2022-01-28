
obj-m += wrapfs.o
wrapfs-objs := dentry.o file.o inode.o main.o super.o lookup.o mmap.o

all:
	make -C /lib/modules/5.13.0-22-generic/build M=$(PWD) modules

clean:
	make -C /lib/modules/5.13.0-22-generic/build M=$(PWD) clean
    