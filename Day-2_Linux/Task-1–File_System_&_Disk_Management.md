# Task-1–File_System_&_Disk_Management.md

1. Listed all block devices and identify available disks
command:- lsblk -f
<img width="858" height="203" alt="image" src="https://github.com/user-attachments/assets/55b82eeb-8449-4db8-ae89-3a8e4eca0246" />

--------
2. Created ebs vloume and attached to the ec2 instance
<img width="1856" height="443" alt="image" src="https://github.com/user-attachments/assets/6d8cc305-2ad0-44c0-b77a-fa86dbfc8897" />
<img width="669" height="206" alt="image" src="https://github.com/user-attachments/assets/fe5fa279-cb9d-43c9-a15a-3503fc84ae82" />

------
3. Created partition
(""sudo fdisk /dev/nvme1n1
n   # create new partition
p   # make it a primary partition
1   # partition number
<Enter> # default start
<Enter> # default end (use full size)
w   # write changes and exit"")
<img width="1444" height="1019" alt="image" src="https://github.com/user-attachments/assets/6d3a3201-43f2-4b7e-83b4-4460f156999b" />

-------
4. Formated partition with ext4 and mounted to /mnt/data
Command: sudo mkfs.ext4 /dev/nvme1n1
         sudo mkdir -p /mnt/data
          sudo mount /dev/xvdb1 /mnt/data
<img width="1307" height="1149" alt="image" src="https://github.com/user-attachments/assets/da1620b3-f6e7-4e7b-943b-8860dd27b293" />

---------
5. Added entry in /etc/fstab for persistent mounting.(Autometic mount after restart)
<img width="1348" height="366" alt="image" src="https://github.com/user-attachments/assets/83291308-ed27-46c9-89c8-ce522ddfdf37" />
<img width="1126" height="147" alt="image" src="https://github.com/user-attachments/assets/a0f31736-0764-4bc3-af5d-7f99bc157284" />

-----------

Step	Command	Description
1	lsblk -f	List disks & filesystems
2	fdisk /dev/xvdb	Create partition
3	mkfs.ext4	Format as ext4
4	mount	Mount disk to directory
5	df -h	Verify mount status
6	blkid	Get disk UUID
7	/etc/fstab	Make mount permanent
8	mount -a	Test persistent mount
