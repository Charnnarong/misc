# Centos Quick guide.
**************
```bash
tree -C -L 1 /
```

| dirctory        | Description  |
| ------------- |:-------------:| 
 /    | root,higest level in the hierarchy 
 /bin     | command binary (grep,awk,etc.)
/boot | boot loader , kernel
/dev | sytem device (disk,etc)
/etc | system configuration file
/home | user home directories
/lib | library for system binaries
/media | mount point for removable media
/opt | third-party software packages
/proc, /run | system and process information
/root | root user home folder
/run | information about running process
/sbin | system binary
/srv | files for various services
/sys | similar to /proc
/tmp | temporary files
/user | another place for applications
/var | varialbe files (e.g. logs)

--------------

###Change localhost name
```bash
vi /etc/hostname
```
1. Change the name as needed.
2. add host name mapping
```
vi /etc/host
```
3. restart system
```
shutdown -r now
```


-----------------
