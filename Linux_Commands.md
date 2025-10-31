# 🧭 Linux Administration Bootcamp — Command Reference

---

## **1. Accessing Linux Servers**

| Command | Description |
|----------|-------------|
| `ssh user@<ip>` | Connect securely to a remote Linux system over SSH. |
| `ssh -i key.pem ubuntu@<ip>` | Connect using a private key (AWS EC2 style). |
| `scp file.txt user@<ip>:/tmp/` | Copy files securely to/from remote servers. |
| `rsync -av /src/ user@<ip>:/dest/` | Synchronize files efficiently over SSH. |

---

## **2. Linux Distribution & Package Management**

| Command | Description |
|----------|-------------|
| `cat /etc/os-release` | Display distribution name and version details. |
| `sudo apt update` | Refresh the local package database. |
| `sudo apt upgrade` | Install the latest available package updates. |
| `sudo apt install <pkg>` | Install new software package. |
| `sudo apt remove <pkg>` | Remove installed package but keep config. |
| `sudo apt purge <pkg>` | Remove package and its configuration files. |
| `apt show <pkg>` | Display detailed package information. |
| `apt search <pkg>` | Search for available packages by name or description. |
| `apt list --installed` | List all installed packages on the system. |
| `dpkg -l | grep <pkg>` | Check if a package is installed using dpkg. |

---

## **3. Filesystem Layout**

| Path | Description |
|------|-------------|
| `/bin`, `/sbin` | Essential user and system binaries. |
| `/etc` | Configuration files for system and services. |
| `/home` | Home directories for users. |
| `/var` | Variable data (logs, mail, spool). |
| `/usr` | User programs and shared data. |
| `/opt` | Optional third-party software. |
| `/tmp` | Temporary working directory. |
| `/boot` | Kernel and bootloader files. |

---

## **4. Basic Commands**

| Command | Description |
|----------|-------------|
| `pwd` | Print current working directory. |
| `ls -l` | List files with permissions, ownership, and size. |
| `cd /path` | Change directory. |
| `whoami` | Display current user. |
| `hostnamectl` | Show system hostname and OS info. |
| `man <cmd>` | Open manual page for a command. |
| `history` | Show command execution history. |

---

## **5. Directory Management**

| Command | Description |
|----------|-------------|
| `mkdir /path/newdir` | Create a new directory. |
| `rmdir /path/dir` | Remove empty directory. |
| `cp -r dir1 dir2` | Copy a directory recursively. |
| `mv dir1 /tmp/` | Move or rename a directory. |
| `rm -rf /path/dir` | Remove directory and contents forcefully. |

---

## **6. File Operations**

| Command | Description |
|----------|-------------|
| `touch file.txt` | Create an empty file or update its timestamp. |
| `cat file.txt` | Display entire file contents. |
| `less file.txt` | Scroll through file interactively. |
| `head -n 10 file.txt` | Show first 10 lines of a file. |
| `tail -f /var/log/syslog` | Follow file output in real time. |
| `cp file1 file2` | Copy file to another location. |
| `mv file1 file2` | Rename or move a file. |
| `rm file.txt` | Delete a file. |

---

## **7. File Permissions & Ownership**

| Command | Description |
|----------|-------------|
| `ls -l` | Display file permissions and ownership. |
| `chmod 755 file.sh` | Set permissions (rwx for owner, r-x for others). |
| `chmod u+x,g-w file` | Add execute for user, remove write for group. |
| `chown user:group file` | Change file owner and group. |
| `umask` | Display or set default permission mask for new files. |

---

## **8. Text Editing**

| Command | Description |
|----------|-------------|
| `nano file.txt` | Simple text editor with on-screen shortcuts. |
| `vi file.txt` | Vi/Vim editor for advanced editing and scripting. |
| `emacs file.txt` | Emacs editor for code or text editing. |

---

## **9. Searching & Comparing Files**

| Command | Description |
|----------|-------------|
| `find /etc -name "*.conf"` | Search for files matching a pattern. |
| `grep "error" /var/log/syslog` | Search for a keyword inside files. |
| `grep -ri "failed" /var/log/` | Recursive, case-insensitive search. |
| `diff file1 file2` | Compare files line by line. |
| `cmp file1 file2` | Compare files byte by byte. |

---

## **10. Pipes & Redirection**

| Command | Description |
|----------|-------------|
| `>` | Redirect standard output to file (overwrite). |
| `>>` | Append standard output to a file. |
| `<` | Redirect input from a file. |
| `2>` | Redirect error output. |
| `ls /etc | grep ssh` | Pipe output between commands. |
| `ls >out.txt 2>&1` | Combine stdout and stderr into one file. |

---

## **11. File Compression**

| Command | Description |
|----------|-------------|
| `tar -czvf archive.tar.gz /dir` | Create compressed tar archive. |
| `tar -xzvf archive.tar.gz` | Extract compressed archive. |
| `gzip file` | Compress file using gzip. |
| `gunzip file.gz` | Decompress gzip file. |
| `zip -r archive.zip /dir` | Create ZIP archive. |
| `unzip archive.zip` | Extract ZIP archive. |

---

## **12. Shell Customization & Shortcuts**

| Command | Description |
|----------|-------------|
| `alias ll='ls -l'` | Create command shortcut. |
| `unalias ll` | Remove an alias. |
| `echo $PS1` | Show shell prompt format. |
| `export PS1="\u@\h:\w$ "` | Customize prompt. |
| `source ~/.bashrc` | Reload shell configuration. |
| `!!` | Repeat previous command. |
| `!<num>` | Run specific command from history. |

---

## **13. Scheduling & Automation**

| Command | Description |
|----------|-------------|
| `crontab -e` | Edit user’s cron jobs. |
| `crontab -l` | List cron jobs for current user. |
| `systemctl list-timers` | Show active systemd timers. |
| `at 15:00` | Schedule a one-time task at a specific time. |
| `sudo systemctl restart cron` | Restart cron service. |

---

## **14. User & Group Management**

| Command | Description |
|----------|-------------|
| `sudo adduser devops` | Create new user interactively. |
| `sudo deluser devops` | Delete a user account. |
| `sudo groupadd admins` | Create new group. |
| `sudo usermod -aG admins devops` | Add user to group. |
| `id devops` | Display user ID and group memberships. |
| `su - username` | Switch user. |
| `sudo visudo` | Edit sudoers file safely. |

---

## **15. Process & Job Management**

| Command | Description |
|----------|-------------|
| `ps aux` | List all running processes. |
| `top` | Monitor live system processes. |
| `htop` | Interactive process viewer. |
| `kill -9 <PID>` | Terminate process by PID. |
| `jobs` | List background jobs. |
| `fg %1` | Bring background job to foreground. |
| `bg %1` | Resume stopped job in background. |
| `nice -n 10 command` | Set process priority. |

---

## **16. Boot Process & Services**

| Command | Description |
|----------|-------------|
| `systemctl status ssh` | Check service status. |
| `sudo systemctl start nginx` | Start a service. |
| `sudo systemctl enable nginx` | Enable service to start at boot. |
| `sudo systemctl disable nginx` | Disable service on boot. |
| `journalctl -xe` | View system logs and errors. |
| `dmesg | less` | Review kernel and boot messages. |
| `systemctl get-default` | Show default boot target. |

---

## **17. Disk Management**

| Command | Description |
|----------|-------------|
| `lsblk` | Display block devices and mount points. |
| `sudo fdisk -l` | List disk partitions. |
| `sudo mkfs.ext4 /dev/xvdf1` | Format partition with ext4 filesystem. |
| `sudo mount /dev/xvdf1 /mnt` | Mount partition to directory. |
| `sudo umount /mnt` | Unmount filesystem. |
| `df -h` | Show mounted filesystems and space usage. |
| `du -sh /var/log` | Show disk usage for directory. |

---

## **18. Logical Volume Management (LVM)**

| Command | Description |
|----------|-------------|
| `sudo pvcreate /dev/xvdf1` | Initialize a physical volume. |
| `sudo vgcreate vgdata /dev/xvdf1` | Create volume group. |
| `sudo lvcreate -L 10G -n lvapp vgdata` | Create logical volume. |
| `sudo mkfs.ext4 /dev/vgdata/lvapp` | Format logical volume. |
| `sudo lvextend -L +5G /dev/vgdata/lvapp` | Extend logical volume size. |
| `sudo resize2fs /dev/vgdata/lvapp` | Expand filesystem after LV resize. |
| `sudo vgdisplay` | Show volume group info. |

---

## **19. Networking & Firewall**

| Command | Description |
|----------|-------------|
| `ip addr show` | Display all network interfaces and IPs. |
| `ping 8.8.8.8` | Test network connectivity. |
| `ip route` | Show routing table. |
| `nslookup google.com` | Perform DNS lookup. |
| `sudo ufw status` | Check firewall rules. |
| `sudo ufw allow 80/tcp` | Allow HTTP traffic. |
| `sudo systemctl restart networking` | Restart network service. |

---
