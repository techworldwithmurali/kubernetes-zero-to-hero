### Linux Command Guide for DevOps Engineers and System Administrators

**Description:**

- A practical guide for DevOps Engineers and System Administrators, this Linux Command Guide covers essential commands for system management, troubleshooting, and automation.
- Perfect for students and professionals, it offers easy-to-follow instructions on file handling, user management, system monitoring, and cloud-related tasks, helping you boost your command-line skills for real-world applications.

| **Category**               | **Command**                | **Description**                                             |
|----------------------------|----------------------------|-------------------------------------------------------------|
| **Linux Basic Commands**    | pwd                        | Print the current working directory.                        |
|                            | cd                         | Change the current directory.                               |
|                            | ls                         | List files and directories in the current directory.       |
|                            | cal                        | Display the calendar.                                       |
|                            | date                       | Display the current date and time.                          |
|                            | history                    | Show the history of executed commands.                      |
|                            | clear                      | Clear the terminal screen.                                  |
|                            | man                        | Show the manual of a specific command (e.g., man ls).        |
|                            | alias                      | Create a shortcut for commands.                             |
|                            | unalias                    | Remove an alias for a command.                              |
|                            | echo                       | Print a message or variable value to the terminal.          |
|                            | uptime                     | Display how long the system has been running.               |
| **System Info Commands**    | lscpu                      | Display CPU details.                                        |
|                            | cat /proc/cpuinfo          | Show detailed CPU information.                              |
|                            | free -h                    | Show memory details in a human-readable format.             |
|                            | cat /proc/meminfo          | Display detailed memory information.                        |
|                            | uname                      | Display system information such as the kernel name.         |
|                            | hostname                   | Show the system hostname.                                   |
|                            | ping                       | Check the connectivity to a host.                           |
|                            | curl                       | Transfer data from or to a server.                          |
|                            | wget                       | Download files from the internet.                           |
|                            | who                         | Show who is currently logged in.                            |
|                            | whoami                     | Display the current logged-in user.                          |
|                            | id                         | Display user ID and group ID information.                   |
| **Search/Utility Commands** | grep                       | Search for patterns in files or input streams.              |
|                            | egrep                      | Extended version of grep with support for additional regex patterns. |
|                            | fgrep                      | Fixed string search (no regex support).                     |
|                            | find                       | Search for files and directories based on various criteria. |
|                            | locate                     | Quickly find files using a pre-built database.              |
|                            | which                      | Locate the executable file of a command.                    |
|                            | xargs                      | Pass arguments from one command to another.                 |
|                            | sort                       | Sort lines in a file or input.                              |
|                            | uniq                       | Remove duplicate lines from sorted data.                    |
|                            | awk                        | Process and analyze text files or input data.               |
|                            | sed                        | Edit text streams or files.                                 |
| **Linux Directory Structure** | Directory Structure        | Understand Linux directories like /home, /etc, /var, /usr, etc. |
| **Working with Files**      | touch                      | Create empty files or update timestamps.                    |
|                            | cat                        | View the content of files.                                  |
|                            | vim                        | Edit files using the Vim editor.                            |
|                            | nano                       | Edit files using the Nano editor.                           |
|                            | less                       | View file content with navigation support.                  |
|                            | more                       | View file content one screen at a time.                     |
| **Working with Directories** | mkdir                      | Create new directories.                                     |
|                            | rmdir                      | Remove empty directories.                                   |
|                            | cd                         | Navigate between directories.                               |
| **Copy & Move Files**       | cp                         | Copy files and directories.                                 |
|                            | mv                         | Move or rename files and directories.                       |
| **Links and Inodes**        | ln                         | Create hard links for files.                                |
|                            | ln -s                      | Create symbolic (soft) links for files or directories.      |
|                            | ls -i                      | View inode numbers of files.                                |
| **File Permissions**        | chmod                      | Modify file and directory permissions.                      |
|                            | umask                      | Set default permissions for newly created files.            |
|                            | stat                       | Display detailed file permissions and metadata.             |
| **File Ownership**          | chown                      | Change file and directory ownership.                        |
|                            | chgrp                      | Change group ownership of files and directories.            |
| **Remove Files**            | rm                         | Remove files and directories.                               |
|                            | shred                       | Securely delete files by overwriting them.                  |
| **User Management**         | useradd                    | Add a new user to the system.                               |
|                            | passwd                     | Change a user’s password.                                   |
|                            | usermod                    | Modify an existing user’s details.                          |
|                            | userdel                    | Delete a user from the system.                              |
| **Group Management**        | groupadd                   | Create a new group.                                         |
|                            | groupdel                   | Delete a group.                                             |
| **Process Management**      | ps                         | Display information about active processes.                 |
|                            | top                        | Monitor real-time system processes.                         |
|                            | htop                       | Interactive process viewer with more features than top.      |
|                            | kill                       | Terminate a specific process by PID.                        |
|                            | nice                       | Start a process with a custom priority.                      |
|                            | jobs                       | List all active jobs in the current session.                |
|                            | fg                         | Bring a background job to the foreground.                   |
|                            | bg                         | Resume a suspended job in the background.                   |
|                            | killall                    | Terminate all processes by name.                             |
|                            | pkill                      | Kill processes based on partial names or attributes.        |
|                            | watch                      | Periodically run a command and display the output.          |
| **Package Management**      | yum                        | Install, update, and manage packages on RPM-based systems.   |
|                            | dnf                        | Modern replacement for yum.                                  |
|                            | rpm                        | Install, query, verify, update, and remove RPM packages.    |
|                            | apt-get                    | Install, update, and manage packages on Debian-based systems.|
|                            | snap                       | Manage snap packages (universal Linux packages).            |
|                            | flatpak                    | Manage Flatpak packages for sandboxed applications.         |
| **Archiving & Compression** | tar                        | Archive files into a tarball (e.g., tar -cvf).              |
|                            | zip                        | Compress files into a .zip archive.                         |
|                            | unzip                      | Extract files from a .zip archive.                          |
|                            | gzip                       | Compress files using gzip.                                  |
|                            | gunzip                     | Decompress files compressed with gzip.                      |
|                            | bzip2                      | Compress files using bzip2.                                 |
|                            | bunzip2                    | Decompress files compressed with bzip2.                     |
|                            | xz                         | Compress files using xz.                                    |
|                            | unxz                       | Decompress files compressed with xz.                        |
|                            | 7z                         | Compress and extract files with 7zip.                       |
| **Disk & Space Management** | df                         | Show disk space usage of file systems.                      |
|                            | du                         | Show disk usage of files and directories.                   |
|                            | lsblk                      | List information about block devices.                       |
|                            | blkid                      | Display UUID and other attributes of block devices.         |
|                            | mount                      | Mount a file system.                                        |
|                            | umount                     | Unmount a file system.                                      |
|                            | parted                     | Manage partitions interactively.                            |
|                            | fdisk                      | Partition a disk manually.                                  |
| **Networking**              | scp                        | Securely copy files between systems.                        |
|                            | ssh                        | Connect to a remote server via SSH.                         |
|                            | ftp                        | Transfer files using the FTP protocol.                      |
|                            | rsync                      | Synchronize files and directories between systems.          |
|                            | ip                         | Manage and display network interfaces and routing.          |
|                            | ifconfig                   | Display or configure network interfaces.                    |
|                            | netstat                    | Display network connections, routing tables, and statistics.|
|                            | ping                       | Test the connectivity to a network host.                    |
|                            | traceroute                 | Trace the route packets take to a host.                     |
|                            | nslookup                   | Query DNS for information about a domain or IP address.     |
|                            | dig                        | Perform DNS queries and diagnostics.                        |
|                            | curl                       | Transfer data from or to a server.                          |
|                            | wget                       | Download files from the web.                                |
| **Scheduling Tasks**        | cron                       | Automate recurring tasks.                                   |
|                            | crontab                    | Manage cron job schedules for users.                        |
|                            | at                         | Schedule one-time tasks to run in the future.               |
|                            | systemctl                  | Schedule and manage systemd timers.                         |
| **Monitoring Tools**        | iotop                       | Monitor disk I/O usage.                                     |
|                            | nmon                        | Monitor CPU, memory, network, and disk usage in real-time.  |
|                            | vmstat                      | View system performance and resource usage statistics.      |
|                            | dstat                       | View comprehensive system resource usage in real-time.      |
|                            | free                        | Display memory usage.                                       |
|                            | uptime                     | Show system uptime and load averages.                       |
|                            | top                         | Monitor system processes and resource usage.                |
|                            | htop                        | Interactive process viewer with more features than top.     |
|                            | sar                         | Collect, report, and save system activity.                  |
