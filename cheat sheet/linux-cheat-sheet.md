
| **Category**                  | **Command**            | **Description**                                                                 |
|-------------------------------|------------------------|---------------------------------------------------------------------------------|
| **Linux Overview**            | Overview              | Understanding the Linux operating system, its architecture, and usage.         |
| **Linux Basic Commands**      | `pwd`                 | Print the current working directory.                                           |
|                               | `cd`                  | Change the current directory.                                                  |
|                               | `ls`                  | List files and directories in the current directory.                           |
|                               | `cal`                 | Display the calendar.                                                          |
|                               | `date`                | Display the current date and time.                                             |
|                               | `history`             | Show the history of executed commands.                                         |
|                               | `clear`               | Clear the terminal screen.                                                     |
|                               | `man`                 | Show the manual of a specific command (e.g., `man ls`).                        |
|                               | `alias`               | Create a shortcut for commands.                                                |
|                               | `unalias`             | Remove an alias for a command.                                                 |
|                               | `echo`                | Print a message or variable value to the terminal.                             |
|                               | `uptime`              | Display how long the system has been running.                                  |
| **System Info Commands**      | `lscpu`               | Display CPU details.                                                           |
|                               | `cat /proc/cpuinfo`   | Show detailed CPU information.                                                 |
|                               | `free -h`             | Show memory details in a human-readable format.                                |
|                               | `cat /proc/meminfo`   | Display detailed memory information.                                           |
|                               | `uname`               | Display system information such as the kernel name.                            |
|                               | `hostname`            | Show the system hostname.                                                      |
|                               | `ping`                | Check the connectivity to a host.                                              |
|                               | `curl`                | Transfer data from or to a server.                                             |
|                               | `wget`                | Download files from the internet.                                              |
|                               | `who`                 | Show who is currently logged in.                                               |
|                               | `whoami`              | Display the current logged-in user.                                            |
|                               | `id`                  | Display user ID and group ID information.                                      |
| **Search/Utility Commands**   | `grep`                | Search for patterns in files or input streams.                                 |
|                               | `egrep`               | Extended version of `grep` with support for additional regex patterns.         |
|                               | `fgrep`               | Fixed string search (no regex support).                                        |
|                               | `find`                | Search for files and directories based on various criteria.                    |
|                               | `locate`              | Quickly find files using a pre-built database.                                 |
|                               | `which`               | Locate the executable file of a command.                                       |
|                               | `xargs`               | Pass arguments from one command to another.                                    |
|                               | `sort`                | Sort lines in a file or input.                                                 |
|                               | `uniq`                | Remove duplicate lines from sorted data.                                       |
|                               | `awk`                 | Process and analyze text files or input data.                                  |
|                               | `sed`                 | Edit text streams or files.                                                    |
| **Linux Directory Structure** | Directory Structure   | Understand Linux directories like `/home`, `/etc`, `/var`, `/usr`, etc.        |
| **Working with Files**        | `touch`               | Create empty files or update timestamps.                                       |
|                               | `cat`                 | View the content of files.                                                     |
|                               | `vim`                 | Edit files using the Vim editor.                                               |
|                               | `nano`                | Edit files using the Nano editor.                                              |
|                               | `less`                | View file content with navigation support.                                     |
|                               | `more`                | View file content one screen at a time.                                        |
| **Working with Directories**  | `mkdir`               | Create new directories.                                                        |
|                               | `rmdir`               | Remove empty directories.                                                      |
|                               | `cd`                  | Navigate between directories.                                                  |
| **Copy & Move Files**         | `cp`                  | Copy files and directories.                                                    |
|                               | `mv`                  | Move or rename files and directories.                                          |
| **Links and Inodes**          | `ln`                  | Create hard links for files.                                                   |
|                               | `ln -s`               | Create symbolic (soft) links for files or directories.                         |
|                               | `ls -i`               | View inode numbers of files.                                                   |
| **File Permissions**          | `chmod`               | Modify file and directory permissions.                                         |
|                               | `umask`               | Set default permissions for newly created files.                               |
|                               | `stat`                | Display detailed file permissions and metadata.                                |
| **File Ownership**            | `chown`               | Change file and directory ownership.                                           |
|                               | `chgrp`               | Change group ownership of files and directories.                               |
| **Remove Files**              | `rm`                  | Remove files and directories.                                                  |
|                               | `shred`               | Securely delete files by overwriting them.                                     |
| **User Management**           | `useradd`             | Add a new user to the system.                                                  |
|                               | `passwd`              | Change a user’s password.                                                      |
|                               | `usermod`             | Modify an existing user’s details.                                             |
|                               | `userdel`             | Delete a user from the system.                                                 |
| **Group Management**          | `groupadd`            | Create a new group.                                                            |
|                               | `groupdel`            | Delete a group.                                                                |
| **Process Management**        | `ps`                  | Display information about active processes.                                    |
|                               | `top`                 | Monitor real-time system processes.                                            |
|                               | `htop`                | Interactive process viewer with more features than `top`.                      |
|                               | `kill`                | Terminate a specific process by PID.                                           |
|                               | `nice`                | Start a process with a custom priority.                                        |
| **Process Management**        | `jobs`               | List all active jobs in the current session.                                   |
|                               | `fg`                 | Bring a background job to the foreground.                                     |
|                               | `bg`                 | Resume a suspended job in the background.                                     |
|                               | `killall`            | Terminate all processes by name.                                              |
|                               | `pkill`              | Kill processes based on partial names or attributes.                          |
|                               | `watch`              | Periodically run a command and display the output.                            |
| **Package Management**        | `yum`                | Install, update, and manage packages on RPM-based systems.                    |
|                               | `dnf`                | Modern replacement for `yum`.                                                 |
|                               | `rpm`                | Install, query, verify, update, and remove RPM packages.                      |
|                               | `apt-get`            | Install, update, and manage packages on Debian-based systems.                 |
|                               | `snap`               | Manage snap packages (universal Linux packages).                              |
|                               | `flatpak`            | Manage Flatpak packages for sandboxed applications.                           |
| **Archiving & Compression**   | `tar`                | Archive files into a tarball (e.g., `tar -cvf`).                              |
|                               | `zip`                | Compress files into a .zip archive.                                           |
|                               | `unzip`              | Extract files from a .zip archive.                                            |
|                               | `gzip`               | Compress files using gzip.                                                    |
|                               | `gunzip`             | Decompress files compressed with gzip.                                        |
|                               | `bzip2`              | Compress files using bzip2.                                                   |
|                               | `bunzip2`            | Decompress files compressed with bzip2.                                       |
|                               | `xz`                 | Compress files using xz.                                                      |
|                               | `unxz`               | Decompress files compressed with xz.                                          |
|                               | `7z`                 | Compress and extract files with 7zip.                                         |
| **Disk & Space Management**   | `df`                 | Show disk space usage of file systems.                                        |
|                               | `du`                 | Show disk usage of files and directories.                                     |
|                               | `lsblk`              | List information about block devices.                                         |
|                               | `blkid`              | Display UUID and other attributes of block devices.                           |
|                               | `mount`              | Mount a file system.                                                          |
|                               | `umount`             | Unmount a file system.                                                        |
|                               | `parted`             | Manage partitions interactively.                                              |
|                               | `fdisk`              | Partition a disk manually.                                                    |
| **Networking**                | `scp`                | Securely copy files between systems.                                          |
|                               | `ssh`                | Connect to a remote server via SSH.                                           |
|                               | `ftp`                | Transfer files using the FTP protocol.                                        |
|                               | `rsync`              | Synchronize files and directories between systems.                            |
|                               | `ip`                 | Manage and display network interfaces and routing.                            |
|                               | `ifconfig`           | Display or configure network interfaces.                                      |
|                               | `netstat`            | Display network connections, routing tables, and statistics.                  |
|                               | `ping`               | Test the connectivity to a network host.                                      |
|                               | `traceroute`         | Trace the route packets take to a host.                                       |
|                               | `nslookup`           | Query DNS for information about a domain or IP address.                       |
|                               | `dig`                | Perform DNS queries and diagnostics.                                          |
|                               | `curl`               | Transfer data from or to a server.                                            |
|                               | `wget`               | Download files from the web.                                                  |
| **Scheduling Tasks**          | `cron`               | Automate recurring tasks.                                                     |
|                               | `crontab`            | Manage cron job schedules for users.                                          |
|                               | `at`                 | Schedule one-time tasks to run in the future.                                 |
|                               | `systemctl`          | Schedule and manage systemd timers.                                           |
| **Monitoring Tools**          | `iotop`              | Monitor disk I/O usage.                                                       |
|                               | `nmon`               | Monitor CPU, memory, network, and disk usage in real-time.                    |
|                               | `vmstat`             | View system performance and resource usage statistics.                        |
|                               | `dstat`              | View comprehensive system resource usage in real-time.                        |
|                               | `free`               | Display memory usage.                                                         |
|                               | `uptime`             | Show system uptime and load averages.                                         |
|                               | `top`                | Monitor system processes and resource usage.                                  |
|                               | `htop`               | Interactive process viewer with more features than `top`.                     |
|                               | `sar`                | Collect, report, and save system activity.                                    |
| **Text Manipulation**         | `awk`                | Process and analyze text data.                                                |
|                               | `sed`                | Perform stream editing on text data.                                          |
|                               | `cut`                | Extract specific columns or fields from text data.                            |
|                               | `paste`              | Merge lines of files together.                                                |
|                               | `sort`               | Sort lines of text.                                                           |
|                               | `uniq`               | Remove duplicate lines from sorted data.                                      |
|                               | `wc`                 | Count words, lines, characters, and bytes in a file.                          |
|                               | `tac`                | Display the contents of a file in reverse order.                              |
|                               | `diff`               | Compare the differences between two files.                                    |
|                               | `cmp`                | Compare two files byte by byte.                                               |
|                               | `comm`               | Compare two sorted files line by line.                                        |
| **Special Utilities**         | `sleep`              | Pause execution for a specified duration.                                     |
|                               | `exit`               | Exit the terminal or script.                                                  |
|                               | `host`               | Perform DNS lookups and display results.                                      |
|                               | `watch`              | Run a command repeatedly at regular intervals.                                |
| **File Systems**              | `fsck`               | Check and repair file system consistency.                                      |
|                               | `mkfs`               | Create a new file system on a partition.                                       |
|                               | `e2fsck`             | Check ext2/ext3/ext4 file system integrity.                                    |
|                               | `tune2fs`            | Adjust tunable parameters on ext file systems.                                 |
|                               | `mount`              | Mount a file system to a directory.                                            |
|                               | `umount`             | Unmount a mounted file system.                                                 |
|                               | `blkid`              | Display block device attributes like UUID and file system type.                |
|                               | `lsblk`              | List all block devices and their associated partitions.                        |
|                               | `df`                 | Display disk space usage of file systems.                                      |
|                               | `du`                 | Display disk usage of files and directories.                                   |
| **System Services**           | `systemctl`          | Manage systemd services and units.                                             |
|                               | `service`            | Manage services (legacy systems).                                              |
|                               | `chkconfig`          | Manage service startup at different runlevels.                                 |
|                               | `journalctl`         | View system logs from systemd.                                                 |
|                               | `dmesg`              | View kernel ring buffer messages.                                              |
|                               | `uptime`             | Display how long the system has been running.                                  |
| **User Management**           | `who`                | Display a list of users currently logged in.                                   |
|                               | `whoami`             | Show the current logged-in user.                                               |
|                               | `id`                 | Show user ID (UID) and group ID (GID) of the current user.                     |
|                               | `passwd`             | Change or update a user password.                                              |
|                               | `usermod`            | Modify user accounts.                                                          |
|                               | `userdel`            | Delete user accounts.                                                          |
|                               | `groupadd`           | Add new groups.                                                                |
|                               | `groupdel`           | Delete groups.                                                                 |
|                               | `groups`             | Show the groups a user belongs to.                                             |
|                               | `finger`             | Display detailed information about system users.                               |
|                               | `last`               | Show the history of user logins.                                               |
| **Permissions & Ownership**   | `chmod`              | Change file and directory permissions.                                         |
|                               | `chown`              | Change file ownership (user and group).                                        |
|                               | `chgrp`              | Change group ownership of a file or directory.                                 |
|                               | `umask`              | Set default permissions for new files and directories.                         |
|                               | `stat`               | Display detailed information about a file or directory.                        |
|                               | `lsattr`             | List file attributes on an ext file system.                                    |
|                               | `chattr`             | Change file attributes on an ext file system.                                  |
| **Monitoring Tools**          | `top`                | Monitor active processes in real-time.                                         |
|                               | `htop`               | Interactive process viewer with extended features.                             |
|                               | `iotop`              | Monitor real-time disk I/O usage.                                              |
|                               | `vmstat`             | Display system performance and resource usage.                                 |
|                               | `sar`                | Collect and display system performance metrics.                                |
|                               | `free`               | Show available and used memory.                                                |
|                               | `uptime`             | Show how long the system has been running and load averages.                   |
|                               | `dstat`              | Display system resource usage (CPU, disk, network).                            |
| **Backup & Restore**          | `rsync`              | Synchronize and back up files or directories.                                  |
|                               | `cp`                 | Copy files and directories.                                                    |
|                               | `tar`                | Archive files into a tarball for backup.                                       |
|                               | `zip`                | Compress files into a `.zip` archive.                                          |
|                               | `gzip`               | Compress files using gzip.                                                     |
|                               | `bzip2`              | Compress files using bzip2.                                                    |
|                               | `xz`                 | Compress files using xz.                                                       |
|                               | `restore`            | Restore files from a backup archive.                                           |
| **Security & Encryption**     | `ssh`                | Securely access remote servers.                                                |
|                               | `scp`                | Securely copy files between systems.                                           |
|                               | `sftp`               | Securely transfer files using SFTP protocol.                                   |
|                               | `gpg`                | Encrypt and sign files using GPG.                                              |
|                               | `openssl`            | Generate and manage encryption keys, certificates, and files.                  |
|                               | `passwd`             | Change or update user passwords.                                               |
| **Networking**                | `ping`               | Check connectivity to a host.                                                  |
|                               | `traceroute`         | Trace the path packets take to a destination.                                  |
|                               | `netstat`            | Show network connections and routing tables.                                   |
|                               | `ss`                 | Display detailed socket statistics.                                            |
|                               | `nslookup`           | Query DNS for domain or IP information.                                        |
|                               | `dig`                | Perform advanced DNS queries.                                                  |
|                               | `ifconfig`           | Display or configure network interfaces.                                       |
|                               | `ip`                 | Show and manipulate network settings.                                          |
|                               | `wget`               | Download files from the web.                                                   |
|                               | `curl`               | Transfer data from or to a server.                                             |
|                               | `nmap`               | Perform network scanning and port discovery.                                   |
|                               | `ethtool`            | Display or change Ethernet device settings.                                    |
| **Service Management**         | `systemctl start`     | Start a service.                                                               |
|                               | `systemctl stop`      | Stop a service.                                                                |
|                               | `systemctl restart`   | Restart a service.                                                             |
|                               | `systemctl status`    | Check the status of a service.                                                 |
|                               | `systemctl enable`    | Enable a service to start on boot.                                             |
|                               | `systemctl disable`   | Disable a service from starting on boot.                                       |
|                               | `service start`       | Start a service (legacy system).                                               |
|                               | `service stop`        | Stop a service (legacy system).                                                |
|                               | `service restart`     | Restart a service (legacy system).                                             |
| **Disk Management**            | `fdisk -l`            | List all partitions and block devices.                                         |
|                               | `parted`              | Interactive partition editor.                                                  |
|                               | `mkfs.ext4`           | Create an ext4 file system.                                                    |
|                               | `mkfs.xfs`            | Create an XFS file system.                                                     |
|                               | `mkfs.btrfs`          | Create a Btrfs file system.                                                   |
|                               | `mount -o loop`       | Mount a file as a loop device.                                                 |
|                               | `swapoff`             | Disable swap space.                                                            |
|                               | `swapon`              | Enable swap space.                                                             |
| **Firewall Management**        | `ufw`                 | Uncomplicated Firewall management tool.                                        |
|                               | `iptables`            | A utility for configuring the Linux kernel firewall.                           |
|                               | `firewalld`           | Firewall daemon used to manage firewall rules dynamically.                      |
|                               | `firewall-cmd`        | Manage firewalld firewall rules.                                               |
|                               | `systemctl restart firewalld` | Restart the firewall service.                                         |
| **System Monitoring**          | `iostat`              | Display CPU and I/O statistics.                                                |
|                               | `mpstat`              | Display CPU performance statistics.                                            |
|                               | `watch`               | Execute a command repeatedly, showing output at regular intervals.             |
|                               | `uptime`              | Show system uptime and load average.                                           |
|                               | `lsof`                | List open files and associated processes.                                      |
|                               | `dmesg`               | Display kernel buffer messages.                                                |
|                               | `htop`                | Interactive process viewer with real-time updates.                             |
|                               | `top`                 | Real-time system monitor for processes and resource usage.                     |
| **Logging and Auditing**       | `journalctl`          | Display logs from the systemd journal.                                         |
|                               | `logrotate`           | Manage log file rotation.                                                      |
|                               | `ausearch`            | Search audit logs for specific events or patterns.                             |
| **System Updates**             | `yum update`          | Update all packages on a Red Hat-based system.                                 |
|                               | `dnf update`          | Update all packages on a Fedora-based system.                                  |
|                               | `apt-get update`      | Update package list on a Debian-based system.                                  |
|                               | `apt-get upgrade`     | Upgrade all installed packages on a Debian-based system.                       |
|                               | `pacman -Syu`         | Update packages on an Arch-based system.                                       |
| **System Reboot and Shutdown** | `reboot`              | Reboot the system.                                                             |
|                               | `shutdown`            | Shut down the system.                                                          |
|                               | `halt`                | Halt the system.                                                               |
|                               | `poweroff`            | Power off the system.                                                          |
| **Backup & Restore**           | `rsync`               | Sync files and directories between locations.                                  |
|                               | `dd`                  | Copy and convert files, commonly used for creating disk images.                |
|                               | `tar -cvf`            | Create a tar archive of files.                                                 |
|                               | `tar -xvf`            | Extract a tar archive.                                                         |
| **User & Group Management**    | `adduser`             | Add a new user (Debian-based systems).                                         |
|                               | `deluser`             | Delete a user (Debian-based systems).                                          |
|                               | `usermod -aG`         | Add a user to a group.                                                         |
|                               | `gpasswd`             | Administer `/etc/group` and group password files.                              |
|                               | `passwd -l`           | Lock a user’s account.                                                         |
| **Advanced File Operations**   | `rsync -avz`          | Archive and compress files using rsync.                                        |
|                               | `cp -r`               | Copy directories and their contents recursively.                               |
|                               | `mv -i`               | Move or rename files interactively.                                            |
|                               | `ln -s`               | Create a symbolic link to a file.                                              |
|                               | `tar -czvf`           | Create a compressed archive using gzip.                                        |
|                               | `zip -r`              | Compress directories into a .zip archive.                                      |
|                               | `find / -name`        | Search for files with a specific name.                                         |
| **Performance Tuning**         | `sysctl`              | Configure kernel parameters at runtime.                                        |
|                               | `ulimit`              | Set user process resource limits.                                              |
|                               | `nice`                | Set process priority for a command.                                            |
|                               | `renice`              | Change the priority of a running process.                                      |
| **Virtualization**             | `virt-manager`        | Manage virtual machines using libvirt.                                         |
|                               | `vagrant`             | Manage virtual machine environments for development.                           |
|                               | `qemu`                | Perform hardware emulation for virtual machines.                               |
