Q1. = B

Q2.
| BIOS  |   UEFI |
| -- | -- |
| -uses the MBR(master boot record ) |                                             -uses the GPT(gui partition table) |
 | -its not an extensible firmware   |                                             - its an extensible firmware        |
| -has a maximum number of partition of 4      |                                 - Maximum number of partition is 128    |
|-old version                                   |                               - new version                          |

Q3.
-use ``lsmod`` command to list all the loaded modules in the system

Q4.
you have to know that all inspection commands are stored in files found in the /proc and /sys directories and these directories act as mount points to filesystems not present in the device partition
/proc
-The /proc directory contains files with information regarding running processes and hardware resources.
-it contains some files like /proc/cpuinfo : which displays all the information about the cpu in the O.S
-/proc also contains information about various kernel data structures, including running processes and configuration.
/sys
-The /sys directory has the specific purpose of storing device information and kernel data related to hardware
-it also contains information about the system and files in the  /sys perform some similar function as the files in the /proc

Q5. = C and B

Q6
you have to know that both apt and dpkg are debian package managers
|apt |dpkg|
| -- | -- |
|apt is a high-level package manager with automatic dependency resolution, |while dpkg is a lower-level tool that requires manual dependency handling.|

Q7.
sudo apt-get upgrade
sudo apt dist-urgrade
sudo apt-get remove --purge

Q8
Create a new file in the ``/etc/yum.repos.d/ directory`` with a .repo extension, for example, example.repo
Open the file in a text editor and add the following configuration:
[example]
name=Example Repository
baseurl=http://repo.example.com
enabled=1
gpgcheck=0  # optional, set to 1 if you want to enable GPG signature checking
Q9. = B

Q10
grep /var/log/syslog/ | wc -l

Q11
|HARD LINK     |                                                                     SOFT LINK|
| -- | -- |
|-imited to the same file system, cannot cross file system boundaries. |          - Can cross file system boundaries, allowing links to files on different file systems or network shares.|
|-Deleting the original file has no effect on the hard link,             |        -Deleting the original file makes the soft link unusable, as it points to a non-existent file.|
as it remains a duplicate with the same contents.
-|Created using the ln command without the -s option.|                            -Created using the ln command with the -s option|
|-Share the same inode number as the original file.              |                -Have their own inode number, distinct from the original file.|

Q12
``find /etc -type f -name "*.conf" -mtime -7``

Q13
The cron daemon is a time-based job scheduler in Unix-like operating systems.
Its primary purpose is to execute commands or scripts at specified times or intervals, allowing system administrators to automate routine tasks, such as backups, log rotations, and maintenance activities.
``0 0 * * * /path/to/backup.sh ``

Q14 = B

Q15
``lsblk -f -o UUID``

Q16
|ext3|ext4|
| -- | -- |
|Ext3 has a maximum file size limit of 16 GB and a maximum partition size limit of 32 TB.|Ext4 has a maximum file size limit of 16 GB and a maximum partition size limit of 16 TB.|

EXT4  is better in ;
-Faster file system checks - ext4 has an enhanced filesystem check (fsck) which is significantly quicker than ext3. ...
-Support for larger file sizes - ext4 supports individual files up to 16 terabytes in size, compared to the 2TB limit of ext3.

Q17
Use ``fdisk`` to list the available disk devices: ``fdisk -l``
Use ``mkfs.ext4`` to format the new partition
Create a mount point for the new partition using ``mkdir``
Open the ``/etc/fstab`` file in a text editor using ``sudo nano /etc/fstab``  
Update the system’s partition table using ``sudo update-initramfs -u``
Verify the mount by checking the /data directory using ``ls /data``

Q18 
The purpose of the ``/etc/fstab`` file is to configure static information about file systems, such as their mount points, file system types, and mount options.

BONUS
 Power-On Self-Test (POST) and Bootloader Selection

    The system’s BIOS or UEFI firmware initializes the hardware, performing a power-on self-test (POST) to check the system’s configuration and detect any issues.
    The BIOS or UEFI firmware searches for a bootable device (e.g., hard drive, solid-state drive, or USB drive) and selects a bootloader (GRUB, LILO, or others) to execute.
 
  Bootloader Execution

    The selected bootloader (GRUB, in most modern Linux distributions) is loaded into memory from the MBR (Master Boot Record) or EFI system partition.
    GRUB displays a boot menu, allowing the user to select an operating system or kernel image to boot.
    GRUB loads the selected kernel image into memory and passes control to it.

Kernel Initialization

    The kernel is loaded into memory and initialized.
    The kernel performs hardware initialization, configuring memory, and setting up the system’s architecture.
    The kernel extracts the initramfs (initial RAM filesystem) from the bootloader, which contains essential drivers and modules needed to mount the root filesystem
    The kernel uses the initramfs to mount the root filesystem (e.g., /dev/sda1) and sets up the system’s root directory.
    The kernel loads additional kernel modules from the /lib/modules directory, as needed.

System Initialization

    The kernel executes the init process (e.g., systemd, sysvinit, or upstart) from the initramfs.
    The init process initializes system services, such as:
        Network interfaces
        Disk partitions
        Filesystems
        System daemons (e.g., sshd, httpd)
    The init process sets up the system’s runtime environment, including setting the system clock, configuring locale settings, and initializing user accounts.

Fully Loaded OS

    The system is now fully initialized and ready for user interaction.
    The user can log in, access the file system, and run applications.






