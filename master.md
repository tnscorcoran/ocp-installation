### copy keys from bastion to master

```
vi .ssh/authorized_keys
```

### disk partition

```
lsblk

fdisk /dev/xvdc
		Welcome to fdisk (util-linux 2.23.2).

		Changes will remain in memory only, until you decide to write them.
		Be careful before using the write command.

		Device does not contain a recognized partition table
		Building a new DOS disklabel with disk identifier 0xa3c54970.

		Command (m for help): n
		Partition type:
		   p   primary (0 primary, 0 extended, 4 free)
		   e   extended
		Select (default p): p
		Partition number (1-4, default 1):
		First sector (2048-167772159, default 2048):
		Using default value 2048
		Last sector, +sectors or +size{K,M,G} (2048-167772159, default 167772159):
		Using default value 167772159
		Partition 1 of type Linux and of size 80 GiB is set
		Command (m for help): w


		The partition table has been altered!

		Calling ioctl() to re-read partition table.
		Syncing disks.

partprobe

mkfs.xfs /dev/xvdc1

blkid /dev/xvdc1
	Copy the UUID

mkdir /exports

vi /etc/fstab
	UUID=<your_UUID> /exports                xfs     defaults        0 0

mount -a

df -h
```