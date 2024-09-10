# Basic Concepts
## What are the key differences between Linux and other operating systems like Windows and macOS?

Linux: Linux is often considered more secure than Windows and macOS due to its robust permissions system, frequent security updates, and open-source nature. macOS: macOS has a reputation for strong security due to Apple's tight control over both the hardware and software ecosystem.

## Describe the Linux file system hierarchy. What are the purposes of directories like /bin, /etc, and /home?

### Describe the Linux file system hierarchy

1. / (Root): 

Primary hierarchy root and root directory of the entire file system hierarchy. 

Every single file and directory start from the root directory.
The only root user has the right to write under this directory.
/root is the root user’s home directory, which is not the same as /

2. /bin : 
Essential command binaries that need to be available in single-user mode; for all users, e.g., cat, ls, cp. 

Contains binary executables.
Common linux commands you need to use in single-user modes are located under this directory.
Commands used by all the users of the system are located here e.g. ps, ls, ping, grep, cp 

3. /boot :
 Boot loader files, e.g., kernels, initrd. 
 

Kernel initrd, vmlinux, grub files are located under /boot
Example: initrd.img-2.6.32-24-generic, vmlinuz-2.6.32-24-generic

4. /dev :
 Essential device files, e.g., /dev/null. 

These include terminal devices, usb, or any device attached to the system.
Example: /dev/tty1, /dev/usbmon0

5. /etc :
 Host-specific system-wide configuration files.

Contains configuration files required by all programs.
This also contains startup and shutdown shell scripts used to start/stop individual programs.
Example: /etc/resolv.conf, /etc/logrotate.conf.

6. /home :
 Users’ home directories, containing saved files, personal settings, etc.

Home directories for all users to store their personal files.
example: /home/kishlay, /home/kv


7. /lib:
 Libraries essential for the binaries in /bin/ and /sbin/.

Library filenames are either ld* or lib*.so.*
Example: ld-2.11.1.so, libncurses.so.5.7

8. /media:
 Mount points for removable media such as CD-ROMs (appeared in FHS-2.3).

Temporary mount directory for removable devices.
Examples, /media/cdrom for CD-ROM; /media/floppy for floppy drives; /media/cdrecorder for CD writer

9. /mnt :
 Temporarily mounted filesystems.

Temporary mount directory where sysadmins can mount filesystems.

10. /opt : 
Optional application software packages.

Contains add-on applications from individual vendors.
Add-on applications should be installed under either /opt/ or /opt/ sub-directory.


11. /sbin : 
Essential system binaries, e.g., fsck, init, route.

Just like /bin, /sbin also contains binary executables.
The linux commands located under this directory are used typically by system administrators, for system maintenance purposes.
Example: iptables, reboot, fdisk, ifconfig, swapon


12. /srv : 
Site-specific data served by this system, such as data and scripts for web servers, data offered by FTP servers, and repositories for version control systems.

srv stands for service.
Contains server specific services related data.
Example, /srv/cvs contains CVS related data.


13. /tmp : 
Temporary files. Often not preserved between system reboots and may be severely size restricted.

Directory that contains temporary files created by system and users.
Files under this directory are deleted when the system is rebooted.

14. /usr : 
Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications. 
 

Contains binaries, libraries, documentation, and source-code for second level programs.
/usr/bin contains binary files for user programs. If you can’t find a user binary under /bin, look under /usr/bin. For example: at, awk, cc, less, scp
/usr/sbin contains binary files for system administrators. If you can’t find a system binary under /sbin, look under /usr/sbin. For example: atd, cron, sshd, useradd, userdel
/usr/lib contains libraries for /usr/bin and /usr/sbin
/usr/local contains user’s programs that you install from source. For example, when you install apache from source, it goes under /usr/local/apache2
/usr/src holds the Linux kernel sources, header-files and documentation. 


15. /proc:
 Virtual filesystem providing process and kernel information as files. In Linux, it corresponds to a procs mount. Generally, automatically generated and populated by the system, on the fly.

Contains information about system process.
This is a pseudo filesystem that contains information about running processes. For example: /proc/{pid} directory contains information about the process with that particular pid.
This is a virtual filesystem with text information about system resources. For example: /proc/uptime



### What are the purposes of directories like /bin, /etc, and /home?
The root directory contains various important directories, such as ' bin ' (which contains essential executables), ' etc ' (which stores configuration files), ' home ' (which holds user home directories), and ' lib ' (which contains shared libraries).


## Explain the concept of a Linux distribution. Name at least three popular Linux distributions and their primary uses.
#### Explain the concept of a Linux distribution
A Linux distribution -- often shortened to "Linux distro" -- is a version of the open source Linux operating system that is packaged with other components, such as an installation programs, management tools and additional software such as the KVM hypervisor.



#### Name at least three popular Linux distributions and their primary uses.
- Ubuntu

Ubuntu is a Linux distribution that has three editions - Desktop, Server, and Core for IoT. Ubuntu provides a user-friendly user interface and comes with free software such as LibreOffice, Firefox, Thunderbird, Transmission, and games like Sudoku and chess. In addition to the user-friendliness, the operating system is known to be more secure than Windows. It is not immune to viruses but it has a significantly lower level of exposure risk to malware or viruses. Plus, it is highly customizable, so you can change your Ubuntu environment so it is more suitable to your needs.

      

- CentOS

CentOS, compared to other Linux distributions, runs faster thanks to its lightweight and reliable software. The operating system has a longer upgrade cycle of about five years. Other distributions tend to have a shorter cycle. This means that those other distros can sometimes be less reliable due to more frequent updates. Because of this, people consider CentOS as a stable operating system.      

- Fedora

Fedora is also regarded as a stable and reliable operating system. Fedora offers many graphical tools and useful software for your office work, virus protection, system management, media play, education, and more. Thanks to its popularity, it is supported by a large community, which is an important factor when you choose open-source software.


# User and File Management

## How do you create and manage users and groups in Linux? Provide commands for adding, deleting, and modifying users.

#### How do you create and manage users and groups in Linux? 
- Create and modify groups. To add a group in Linux, use the groupadd command: $ sudo groupadd demo. 

- Change the group ID. You can change the group ID of any group with the groupmod command and the --gid or -g option: $ sudo groupmod -g 1011 demo1.
- Rename a group. 
- Add and remove users from a group. 
- Delete a group.

#### Provide commands for adding, deleting, and modifying users.
- useradd : Create new user accounts.

- usermod : Modify existing user accounts and manage group memberships.

- deluser : Delete user accounts.

## What are file permissions in Linux? Explain the meaning of rwx and how to change permissions using chmod.

#### What are file permissions in Linux?
File permissions are an essential part of managing and maintaining a Linux system because they control the access to files and directories and ensure the security of the Linux system and the data stored in the files and directories.

#### Explain the meaning of rwx
rwx means that this user can read, write and execute this file. Group permissions(r-x) - Permissions for other users in the file's group. r-x means that the user can read and execute the file but cannot write to it. Other user permissions(r-x) - Permissions for users who do not belong to the above categories.

#### Explain how to change permissions using chmod.
To change directory permissions for everyone, use “u” for users, “g” for group, “o” for others, and “ugo” or “a” (for all). chmod ugo+rwx foldername to give read, write, and execute to everyone. chmod a=r foldername to give only read permission for everyone.

## How can you manage file ownership and groups using chown and chgrp commands?

The `chgrp` command in Linux is used to change the group ownership of a file or directory. All files in Linux belong to an owner and a group. You can set the owner by using “chown” command, and the group by the “chgrp” command


# System Administration
## What are system services and daemons in Linux? How do you manage them using systemctl?

#### What are system services and daemons in Linux?
A service doesn't have to be a daemon, but usually is. A user application with a GUI could have a service built into it: for instance, a file-sharing application. Daemons are processes running in the background and are not in your face. They do certain tasks at set times or responds to certain events.

#### How do you manage them using systemctl?
To start and stop systemd services, use the following commands:

- To start a systemd service: > sudo systemctl start SERVICE.

- To check the status of a systemd service: > sudo systemctl status SERVICE.

- To stop a currently running systemd 
service: > sudo systemctl stop SERVICE.


## Explain how to schedule tasks in Linux using cron and at.

Setting Up a Cron Job

- Write a Script (Optional) This section explains how to create an example script. 
- Create or Edit Crontab File. Open the crontab configuration file for the current user by entering the following command: crontab -e. 
- Create the Cron Job. 
- Output (Optional) 
- Save. 
- Check Active Cron Jobs.

## What is the purpose of the /etc/fstab file? How do you mount and unmount file systems?

#### What is the purpose of the /etc/fstab file?
The fstab (/etc/fstab) (or file systems table) file is a system configuration file on Debian systems. The fstab file typically lists all available disks and disk partitions, and indicates how they are to be initialized or otherwise integrated into the overall system's file system.


#### How do you mount and unmount file systems?
- Mounting a File System

To mount a file system in a given location (mount point), use the mount command in the following form:

mount [OPTION...] DEVICE_NAME DIRECTORY
Copy
Once the file system is attached, the mount point becomes the root directory of the mounted file system.

For example, to mount the /dev/sdb1 file system to the /mnt/media directory you would use:

sudo mount /dev/sdb1 /mnt/media
Copy
Usually when mounting a device with a common file system such as ext4 or xfs the mount command will auto-detect the file system type. However, some file systems are not recognized and need to be explicitly specified.

Use the -t option to specify the file system type:

mount -t TYPE DEVICE_NAME DIRECTORY
Copy
To specify additional mount options , use the -o option:

mount -o OPTIONS DEVICE_NAME DIRECTORY
Copy
Multiple options can be provided as a comma-separated list (do not insert a space after a comma).

You can get a list of all mount options by typing man mount in your terminal.

- Mounting a File System using /etc/fstab

When providing just one parameter (either directory or device) to the mount command, it will read the content of the /etc/fstab configuration file to check whether the specified file system is listed or not.

If the /etc/fstab contains information about the given file system, the mount command uses the value for the other parameter and the mount options specified in the fstab file.

The /etc/fstab file contains a list of entries in the following form:

/etc/fstab
[File System] [Mount Point] [File System Type] [Options] [Dump] [Pass]
Copy
Use the mount command in one of the following forms to attach a file system specified in the /etc/fstab file:

mount [OPTION...] DIRECTORY
mount [OPTION...] DEVICE_NAME


# Networking
## Describe the basic networking commands in Linux such as ifconfig, ip, ping, netstat, and ss.

- ifconfig	Display and manipulate route and network interfaces.

- ip	It is a replacement of ifconfig command.

- ping	To check connectivity between two nodes.

- netstat	Display connection information.

- ss	It is a replacement of netstat.


## How do you configure a static IP address in Linux?

For Debian-based Systems (e.g., Ubuntu)
Edit the Netplan Configuration:

Modern Ubuntu versions use Netplan for network configuration. The configuration files are located in /etc/netplan/. Open the relevant configuration file (usually with a .yaml extension) in a text editor with root privileges. For example:

sudo nano /etc/netplan/01-netcfg.yaml

Modify or add the configuration to specify a static IP address. Here’s a sample configuration:

network:
  version: 2
  ethernets:
    eth0:
      addresses:
        - 192.168.1.100/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4

Save the file and apply the changes with:

sudo netplan apply



## What are firewalls in Linux, and how do you configure them using iptables or firewalld?

#### What are firewalls in Linux
The security system in Linux OS is known as Linux Firewall, which monitors and governs the network traffic (outbound/inbound connections). It can be used to block access to different IP addresses, Specific subnets, ports (virtual points where network connections begin and end), and services.

#### how do you configure them using iptables or firewalld?
1. Instructions
- Step 1: Update your system. 
- Step 2: Install the iptables firewall in Ubuntu. 
- Step 3: Check the current status of iptables. 
- Step 4: Allow traffic on localhost. 
- Step 5: Allow traffic on specific ports. 
- Step 6: Control traffic by IP address. 
- Step 7: Delete unwanted traffic. 
- Step 8: Delete a rule. 

2. Go further.


# Package Management

## What are package managers in Linux? Compare apt, yum, and dnf.

#### What are package managers in Linux?
A package management system or package manager is a group of software tools. It automates the installation process, upgrading process, configuration process, and removing process of the computer programs for an operating system of the computer in an efficient manner.

#### Compare apt, yum, and dnf.

APT is short for Advanced Package Tool. It serves as the default package manager for Debian and, by extension, Debian-based Linux distributions like Ubuntu. Since Ubuntu is the most popular Linux distro, and there are scores of distros based on Ubuntu, APT is the package manager many of us encounter first. Software in Linux comes in different formats, and APT works with the DEB package format in particular.

DNF is the default package manager in Fedora and Fedora-based distros such as Red Hat Enterprise Linux and CentOS. DNF works with the RPM package format.

DNF vs. YUM

DNF's name isn't an acronym. Those three letters are short for "Dandified YUM."

DNF is a rewrite of YUM, the "Yellowdog Updater, Modified." YUM itself was already a rewrite of "Yellowdog UPdater," or YUP, originally developed for Yellow Dog Linux.

While you may see YUM in use on older systems, it has been discontinued in favor of DNF. There isn't much reason to seek out YUM today.


## How do you install, update, and remove packages using a package manager?

To update your package list, run sudo apt update. To install a package, use sudo apt install package_name. To remove a package, use sudo apt remove package_name.


# Monitoring and Performance
## What tools are available in Linux for monitoring system performance? Describe the use of top, htop, vmstat, and iostat.

#### What tools are available in Linux for monitoring system performance?

- Ping Tool
- Traceroute
- CLI Tool
- SNMP Tool
- MAC Address Resolver
- DNS Resolver
- DHCP Scope Monitor
- Port Scanner


#### Describe the use of top, htop, vmstat, and iostat.
- Top is one of the most basic yet powerful tools for performance monitoring in Linux.

- Iostat is part of the sysstat package and is used to monitor system input/output device loading.

- Vmstat reports information about processes, memory, paging, block I/O, traps, and CPU activity.

## How do you check disk usage and availability using commands like df and du?

How to check disk space in Linux with df and du

- The df command. The df (disk free) command is used to get a report of the total, used and available space on mounted file systems. 

- The du command. Unlike df , the du (disk usage) command is used to estimate the disk space usage of the specified file or directory.

# Security

## Explain the concept of SSH. How do you set up an SSH server and client in Linux?

####  Explain the concept of SSH

SSH or Secure Shell is a network communication protocol that enables two computers to communicate (c.f http or hypertext transfer protocol, which is the protocol used to transfer hypertext such as web pages) and share data.

####  How do you set up an SSH server and client in Linux?

- Step1: Install and enable SSH Server. 

- Step2: Enable SSH Protocol Version 2. 

- Step 3: Customize the default SSH port (22) 

- Step4: Disable root login (SSH) 

- Step 5: Use ssh keys (Public and Private)

- Step 6: Disable X11 Forwarding.

- Step 7: Disable Empty Passwords.

- Step 8: Set Max Authentication Attempts

- Step 9: Allow only Specific IP Address

- Step 10: Set Idle Timeout


## What are SELinux and AppArmor? How do they enhance security in a Linux system?

#### What are SELinux and AppArmor?

AppArmor and SELinux are examples of Mandatory Access Control (MAC) systems. These systems differ from other security controls (which are generally called Discretionary Access Control (DAC) systems) in that, generally, the user can't change their operation. File permissions are one example of a DAC system.

#### How do they enhance security in a Linux system?

SELinux, on the other hand, is a completely separate system that does not use the preexisting file access controls. While SELinux uses the type enforcement system to provide security on the servers, AppArmor does not assign types and instead uses configuration files to grant, restrict and deny access.

# Backup and Recovery

## How do you perform backups in Linux? Describe the use of tools like rsync, tar, and dd.

#### How do you perform backups in Linux?
To Back Up Data on Linux, the following guidelines should be used properly.
- Open Deja-Dup application.

- Click on the Create First Back Up.

- Click on Forward.


#### Describe the use of tools like rsync, tar, and dd.
Using rsync for Backup

Basic usage involves a simple command structure:

rsync [options] source destination

For backups, common options include -a for archival mode and -z for compression.

Advanced usage involves options like --delete for mirroring source and destination and --exclude for omitting files.

Whether it's backing up personal files to an external drive or synchronizing data across networked computers, rsync's flexibility makes it ideal for diverse backup scenarios.

Creating tar Backups

The basic command structure is:

tar [options] [archive-name] [files or directories]

For full system backups, a common command is:

tar -cvpzf backup.tar.gz /path/to/directory

Automating tar backups can be achieved with cron jobs, scheduling regular backups without manual intervention.

tar works seamlessly with gzip and bzip2, allowing for compressed backups, saving space, and speeding up transfer rates.

Using dd command we can do:

- Backing up and restoring an entire hard drive or a partition.

- Creating virtual filesystem and backup images of CD or DVDs called ISO files

- Copy regions of raw device files like backing up MBR (master boot record).

- Converting data formats like ASCII to EBCDIC.


## What are some strategies for system recovery in case of a failure?

- Make the service fail-safe

- Track complaints

- Take immediate action

- Explain the situation to the customer

- Treat customers nicely

- Forge a strong relationship with customers

- Customer experience after service recovery







