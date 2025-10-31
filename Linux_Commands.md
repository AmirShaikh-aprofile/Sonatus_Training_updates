## Linuc_Commands

## 📂 2. File System & Disk Management

| Task / Area | Command | Description |
|-------------|---------|-------------|
| List block devices | `lsblk` | Show all disks and partitions |
| Partition disk | `fdisk /dev/xvdb` | Create, delete, or modify partitions |
| Format partition | `mkfs.ext4 /dev/xvdb1` | Format partition with ext4 filesystem |
| Mount filesystem | `mount /dev/xvdb1 /mnt/data` | Mount disk to a directory |
| Persistent mount | Edit `/etc/fstab` | Ensure disk mounts at boot |
| Check disk usage | `df -h` | Show filesystem usage |
| Check folder size | `du -sh /var/*` | Disk usage per folder |
| Show UUID | `blkid` | Get unique disk identifiers |
| Tune filesystem | `tune2fs -L label /dev/xvdb1` | Modify filesystem label or parameters |

---

## 💾 3. LVM (Logical Volume Management)

| Task / Area | Command | Description |
|-------------|---------|-------------|
| Create physical volume | `pvcreate /dev/xvdb` | Prepare disk for LVM |
| Create volume group | `vgcreate vgdata /dev/xvdb` | Create LVM volume group |
| Create logical volume | `lvcreate -n lvapps -L 1G vgdata` | Create logical volume |
| Extend LV | `lvextend -L +500M /dev/vgdata/lvapps` | Increase LV size |
| Reduce LV | `lvreduce -L -500M /dev/vgdata/lvapps` | Decrease LV size |
| Create snapshot | `lvcreate -s -n lvapps_snap -L 1G /dev/vgdata/lvapps` | Take LV snapshot |
| Move LVM data | `pvmove /dev/xvdb /dev/xvdc` | Migrate data between PVs |

---

## ⚙️ 3. Boot Process & System Services

| Task / Area | Command | Description |
|-------------|---------|-------------|
| View boot logs | `journalctl -b` | Logs from current boot |
| Check failed services | `systemctl --failed` | List failed systemd services |
| Service status | `systemctl status <service>` | Show service info & logs |
| Reload systemd | `systemctl daemon-reload` | Reload systemd after changes |
| Start service | `systemctl start custom.service` | Launch service manually |
| Enable auto-start | `systemctl enable custom.service` | Start service on boot |
| Stop/disable service | `systemctl stop/disable <service>` | Manage service lifecycle |

---

## 🌐 4. Networking

| Task / Area | Command | Description |
|-------------|---------|-------------|
| Check IPs | `ip addr show` | Show network interfaces & IPs |
| Check routes | `ip route show` | Display routing table |
| Check DNS | `cat /etc/resolv.conf` | Show DNS servers |
| Test connectivity | `ping -c 4 8.8.8.8` | Test network reachability |
| Test name resolution | `pi
