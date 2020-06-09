# **Linux**


## networking trouble shooting 

### 

## Manage package

### Debian package

- Old

	- dpkg

- New

	- APT

		- install

		- Remove

		- Purge

		- Show 

		- Version

		- Update

		- Upgrade

		- /etc/apt/sources.list.d/

### Red hat package

- rpm

	- option 

		- i 

		- e 

		- v 

		- h 

		- V

		- q 

		- U

		- F

- .rpm

- YUM

	- Handle software dependencies

	- repositories 

	- Subcommands 

		- install 

		- Local install

		- Remove

		- Update

		- Info

		- Provides

	- Repositories 

		- /etc/yum.repos.d/

	- Sync online repo to local repo

		- mirroring

		- reposync 

- Improved version

	- DNF

- also support

	- Zypper 

		- openSUSE

### Repositories

- Local

- Vendor

- Centralized internal

### Automatically download

- wget 

- curl 

## Linux boot components

### booting

### Boot loader

- Boot sector program

- Second stage boot loader

- Boot loader installer

### Firmware

- BIOS

	- Test all the hardware components

	- Hardware level

- UEFI

	- Newer

	- Faster

	- Hold more memory

- Password protection

### Boot options

- ISO image

- PXE

	- Preboot execution environment

	- TFTP

- HTTP/FTP

	- More secure than PXE

- NFS server

### sectors

- Many sectors

	- Track

### partition types

- MBR

	- master boot record

	- MBR boot sector

		- Boot loader

			- Load the os into memory

		- partition tables

		- disvantage

			- Max 2TB

			- Max 4 primary partition

			- Boot data stored in one sector

- GPT

	- GUID partition table

	- Part of UEFI standard

	- every partition has GUID

		- Globally unique identifier

	- Stored boot data in different places

- raw partition

	- directly read and write from user, not using cache

### initrd 

- initial ramdisk 

- loaded with kernel

- Two phases

	- One

		- Loaded the main fs and mount /

	- Two

		- User space boot process continues

- initrd image

	- /boot

### mkinitrd 

### /boot/

- grub2

	- grub 

- efi 

	- Boot loader

- vlminuz

	- Contain Linux kernel

- initramfs 

	- initialize a root file on boot

### dracut 

- Generate initramfs image 

### boot process

- BIOS/UEFI

- MBR/GPT

- GRUB2

	- User select os

- initrd/kernel

- systemd 

	- Find default.target

	- /etc/fstab 

### Kernel panic

- Kernel is corrupted

- Systemd isn’t respond

- Kernel can,t mount root file system

- Incompatible hardware loaded

### Grub 2 boot loader

- grub2 install

	- Only BIOS

- boot/grub.cfg

	- Don’t edit this file

- /etc/grub.d/

	- Edit here

- grub2-mkconfig 

## network connections 

### Host name config

- hostnamectl

	- systemctl restart systemd-hostname

### Ip configuration 

### Network manager

- nmcli 

- nmtui 

- nmgui 

### View current in address 

- Old

	- ifconfig 

- new

	- ip 

- iwconfig 

### ethtool 

- manage NIC driver and network config

### brctl 

- OSI layer2

	- MAC address 

### NIC Bonding 

### /etc/sysconfig/ network-scripts/

- Configuration file

### trouble shooting 

- Check physical connection

- NIC on /off

- network interface configuration 

	- IP address 

	- Gate way value 

	- subnet mask 

	- name resolution 

		- ping a destination 

			- host 

			- nslookup 

			- dig

- NIC is detected?

	- ethtool 

## File system structure

### bin

- Command

	- Link to usr

### sbin

- essential for sys boot up

	- Link to usr/bin

### opt 

- Other software install

	- Third party

### boot

### dev

- hardware as file

### etc

- System configuration 

### home

### lib 

- Link to usr

### mnt 

- run 

### proc

- processing 

### sys 

- sys info

### usr 

- read only

	- 

- Stored small program and file that allow all the user to access

### var 

- Temporary 

## permission 

### Change permission

- Default permission

	- umask

		- bashrc

			- /etc

			- ~/.bashrc

	- Default 0666

		- eg. umask 0222

- **chmod**

	- **symbolic mode** 

		- **+**

		- **-**

		- **=**

	- **absolute mode**

		- **4**

		- **2**

		- **1**

- Only the owner and sys administrators can change permission

### special permission

- sticky bit mode

	- root , owner

		- Can Delete

	- User

		- W

		- X

	- +t

- chmod

	- SGID

		- Inherit directory’s group I’d

			- Share directory

	- SUID

		- Act as root

			- passwd

### Access Control List

- custom individual user and group 

	- setfacl 

		- -R

		- -s

		- -m

		- -x

		- -b

	- getfacl 

		- metadata of the object

### Context

- Other

- Owner = user

- Group

### Attributes

- r

- w

- x

### File attritube

- Immutable flag

	- i 

- lsattr 

	- -R

		- Recursively

	- -a

		- All file

	- -d

		- Directories

	- -v

		- version

- chattr 

	- -R

	- -v

	- +i 

	- -i 

### Trouble shooting 

- No i  flag

	- Directory

		- Enter

			- R

			- X

		- Remove

			- W

			- x

	- File 

		- Remove

			- W on directory

		- Create

			- W

			- X

		- execute 

			- R

			- X

## ownership 

### chgrp 

### chown 

## Monitor device

### lsdev 

- Display the hardware information

### lsusb 

### lspci 

### lpq

## Kernel

### Space

- Kernel space

- User space

## Security Linux

### CIA triad

- confidentiality 

- Integrity

- Availability

### Authentication 

- Password

- Tokens

	- one time password

- Biometrics

- Radius

	- Internet protocol provide AAAservice

- LDAP

- Kerberos 

	- SSO

		- Single sign on

- Multi-factory authentication

### Privilege escalation

- User get the resource that they are not allow to get

	- sudo 

	- SUID

	- SGID

### chroot jails

- Control file access by using changing the root directory

	- chroot 

### Encryption 

- LUKS

	- Encrypt storage device

		- 
		  cryptsetup 

### Hashing

### User access security best practice

- Using password in boot loader

- BIOS/UEFI with password

- Not using USB storage

- Not share UID

- PKI for authentication

- Disable ctrl +Alt+Del

- Enable auditd service

- Add the banner message to /etc/issue

	- Banner message = user login message

	- More message

		- /etc/motd 

			- Message of the day

- Disable insecure service

	- FTP

	- Telnet

	- Finger

		- Retrieve the user information and data through internet

	- mail service

		- Sendmail

		- Postfix

### Authentication software 

- Structure

	- PKI

		- Digital signature

			- message digest that have been encrypted with private key

		- Digital certificate

			- Electrical documents contain public key

		- CA

			- issue digital certificate

		- CSR

		- OpenSSL

			- secure data in transit 

			- Secure SSL/TLS protocol

- PAM

	- authentication framework used by applications and services

	- Framework

		- Kerberos

			- user identity

		- LDAP

			- specify what user can login

	- /etc/pam.d/

	- TTY Security

		- /etc/securetty

	- flag 

		- sufficient 

			- only good news

		- optional

			- Don’t tell anything

		- requisite 

			- Tell the bad news later

		- required

	- user lockout

		- pam _tally2 

		- pam_faillock 

			- new

- SSH authentication

	- Key

		- User’s private key

			- id_rsa

		- User’s public key

			- id_rsa.pub

	- sshd_config

		- /etc/ssh/

			- Global config

		- ~/ .ssh/

			- User base

		- ssh/

			- id_rsa

			- id_rsa.pub

			- Server

				- authorized_keys

			- Client 

				- known_hosts

				- config

			- commands

				- ssh-keygen 

				- ssh-copy-id 

					- append user’s public key to server

				- ssh-add 

	- Add the rule for iptables 

		- Configure listenaddress

	- PermitRootLogin no

	- AllowUser administrator

	- systemctl restart sshd

### VPNs - environment

- virtual private network

- client side

	- IPSec

		- Internet protocol security

		- Authentication clients and encrypt data in transit

		- run on   
		  Network layer -layer3

		- two mode

			- transport model

				- only package content encrypted but header not

			- tunnel model

				- Content and header are encrypted

				- site to site VPN

		- Strongswan 

		- require software install 

	- ssl 

		- encrypted protocol 

		- remote access control

		- Application layer -level7

		- Openvpn 

			- /etc/openvpn 

		- website support 

### pty 

### tty 

### Context-Base permissions

- SELinux

	- Three main contexts 

		- User

		- Role

		- Type

	- Mode

		- Disable

			- closed and DAC get in 

		- Enforcing

			- process can’t violate the security policy

		- Permissive

			- When the security broken, sent the message to the user

	- /etc/selinux 

	- inode 

	- Policy

		- targeted

			- run on MAC

			- Others

				- Unconfined mode

				- DAC

			- Set by default

		- strict

			- Run on MAC 

			- Others run on DAC

	- Command

		- setenforce

		- getenforce

		- setsebool 

			- On / off

	- violations 

		- denied access

		- sealert 

			- diagnose issues

			- /var/log/audit/

		- audit2why 

			- make output user friendly 

- AppArmor

	- Debian-based

	- Simple

	- /etc/apparmor.d/

	- Based on path

	- Mode

		- Complain 

			- aa-complain 

		- Enforce 

			- aa-enforce

### MAC

- Mandatory access control

### DAC

### Firewall

- ACL

- iptables 

- UFW

	- Management tool to configure iptables service

- Firewalld service

	- firewall-cmd 

### Netfilter

### IP Forwarding

### IP Sets

- ipset 

### IPSs

### System log

- /var/log 

### tar 

- cpio 

- dd 

- mirrorvg 

## User and group

### User account

- user account types

	- Root user

		- Local admin

		- Super user

		- su

			- change user 

				- -username

		- sudo

			- /etc/sudoers

		- sudoedit 

			- Open using

				- visudo 

		- wheel group

	- Standard user

	- Service user

		- application

		- Account create as a part of services installation process

- useradd

	- /etc/login.deft

	- Custom file

		- /etc/skel 

	- Options

		- -c

			- comment

		- -e

			- Expiration 

		- -s

			- Set default shell

		- -D

			- Default 

- Password

	- Old

		- /etc/passwd 

			- Accounts’ info 

		- passwd

			- root  change

			- everyone see

	- New

		- /etc/shadow

			- root only

	- chage 

		- Option 

			- -E

			- -L

			- -M

			- -m

			- -W

- usermod 

	- /etc/passwd

	- option

		- -c

		- -e

		- -aG

		- -l

- userdel 

	- Delete home directory

		- -r

### Group account

- /etc/group

	- 

- groupadd 

	- -g

	- -f

	- -o

- groupmod 

	- /etc/group

	- Option 

		- -g

		- -n

- groupdel 

### Query

- whoami 

- who 

- w

### last 

- /var/log/wtmp 

- History of login logout

### id 

- UID

- GID

### User profiles

- individual 

	- .bashrc 

	- .bash_profile

		- First time login

- Global

	- /etc/skel 

	- /etc/profile 

	- /etc/profile.d/

		- Recommend

	- /etc/bashrc

		- bash setting

## Managing storage

### File system

- FAT

	- Older

- ext2

- ext3

- ext4

- XFS

### Inodes

- Object that stored the Metadata about the file

### Journaling 

- Pending changing

### Virtual file system 

### Partition 

- Primary

	- Swap

	- Boot

- Extended

	- One but subdivided

- Logical 

### fdisk 

- Option 

	- n

		- New

	- d

		- Delete

	- p

		- List (print)

	- w

		- Write

	- q

		- Cancel

### parted

- Option

	- select 

	- mkpart 

	- print 

	- resizepart

	- rm 

	- quit 

- Management partitions

### partprobe 

- Updated kernel with partition table

### mkfs 

- build file system on partition

- Option

	- -v

	- -V

	- -t

	- fs-options

	- -c

	- -l

### fstab file

- /etc

	- root only

### /dev/

- sda1

	- sd 

		- Controller

	- a

		- First whole drive

	- 1

		- First partition

### Device mapping

### Logical Volume Manager

- /dev/mapper/<volume group name> - <logical volume name>

- Tools

	- PV

	- VG

	- LV

### Mount points

- mount

	- Option 

		- auto

		- noauto 

		- nouser 

		- user

		- exec 

		- noexec 

		- ro

		- rw 

		- sync 

		- async 

- unmount 

- /proc/mounts 

- /proc/partitions 

### block 

- lsblk 

### ext tool

- e2fsck 

- resize2fs 

- tune2fs

	- Configures tunable parameters

- dumpe2fs

	- System info

- fsck 

	- Check integrity of file system 

	- run at boot time

## Compression 

### gzip

### xz 

### bzip2

