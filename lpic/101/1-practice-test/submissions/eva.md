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

Q5. = C

Q6
you have to know that both apt and dpkg are debian package managers
|apt |dpkg|
| -- | -- |
|apt is a high-level package manager with automatic dependency resolution, |while dpkg is a lower-level tool that requires manual dependency handling.|

Q7.

Q8

Q9. = B

Q10
-echo

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





