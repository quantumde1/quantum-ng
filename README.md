# Quantum OS. Updated.
### Content
- partitial ext4 support
- scheduler (/kernel/sched)
- initial ram disk (/initrd)
- shell task (/initrd/sh.c)
- tty character device driver (/kernel/dev/tty.c)
- abstract file operations (/kernel/vfs/file.c)
- interprocess communication (/kernel/ipc)
- architecture support (/arch)
- small c lib with lists support (/lib)

### Info

Target CPU: any i386-compatible.
### Dependencies
Linux lite (support qemu only):
$ sudo apt-get install gcc
$ sudo apt-get install gcc-arm-none-eabi
$ sudo apt-get install qemu
```
```
Ubuntu (support both bochs and qemu):
$ sudo apt-get install gcc
$ sudo apt-get install bochs
$ sudo apt-get install bochs-x
```

### Build sources and run on qemu

```
Qemu x86:
$ mkdir bin
$ sudo make qemu-x86
```

```
Qemu arm:
$ mkdir bin
$ sudo make qemu-arm
```

### Build sources and run on bochs

```
Bochs x86:
$ sudo mkdir bin
$ sudo mkdir /mnt/kernel_u
$ sudo losetup -a               # check loop13 is free
$ sudo losetup -d /dev/loop13   # release it if not free
$ sudo losetup -a               # make shure loop13 is not present
$ sudo make bochs-x86
```

### Shell commands

Proccess list: `ps`
Kill application: `kill <pid>`
Run application(broken): `exec <name.elf>`
Exit(broken, if enable - break kernel): `exit`
Devices: `dev`
Clear: `clear`

P.S
can anyone help with FS? :(
