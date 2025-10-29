# Tasks-1 - User_File_and_Permission_Management.md

1. Create multiple users & groups and confirmed from the /etc/group & passwd
2. 2.Add users to multiple groups and verify memberships.
<img width="868" height="410" alt="image" src="https://github.com/user-attachments/assets/7f4e0665-5341-4d5d-a1a0-4f2a10ea19f0" />

----

3. Practice permission modes (chmod, chown, chgrp).
<img width="488" height="757" alt="image" src="https://github.com/user-attachments/assets/4ea013a0-d265-404b-bdbb-5cf6a6201f06" />
<img width="770" height="724" alt="image" src="https://github.com/user-attachments/assets/5e17dad2-eeaf-48e9-9f0c-155d448d491d" />

-------
4. Implement sticky bits & ACLs on shared directories.
<img width="699" height="454" alt="image" src="https://github.com/user-attachments/assets/36cf2e7a-87f8-474b-8e98-91a413c44898" />

-------
5. Explore file ownership and umask defaults: It determines what permissions are not given to new files and directories by default.
<img width="742" height="490" alt="image" src="https://github.com/user-attachments/assets/b1dc7a66-a36b-4577-a625-dbfb981f8e8c" />

------

⚙️ Key Commands
useradd devops1
passwd devops1
groupadd cloud
usermod -aG cloud devops1
id devops1
chmod 755 /opt/test
chown root:cloud /opt/test
setfacl -m u:devops1:rwx /opt/test
getfacl /opt/test
umask
