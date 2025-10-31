# Task-1–Boot_Process_System_Services

1. Checking boot logs and failed services.
```bash
sudo journalctl -b
```
Shows logs for the current boot session.<br>
  Add -b -1 to see the previous boot:
  <img width="1670" height="426" alt="image" src="https://github.com/user-attachments/assets/09713981-0a8b-47a8-8566-e7cae338eeb9" />

____
- Checking failed services
```bash
systemctl --failed
```
<img width="1178" height="351" alt="image" src="https://github.com/user-attachments/assets/b6696303-2119-4b5d-b7ea-affa083d1db1" />
Lists all units (services, mounts, etc.) that failed to start during boot.
You’ll see columns like UNIT, LOAD, ACTIVE, SUB, DESCRIPTION.

____
- Checking Service Status
sudo systemctl status 'ssh() Servicename'
<img width="1658" height="434" alt="image" src="https://github.com/user-attachments/assets/cbb15afe-cf3e-4a99-93e5-f52d5e239679" />

---------------
2. Created a Custom Systemd Service
- Created the script runs an infinite loop that writes a timestamp to a log every 10 seconds.(With help of chatgpt)

____
- Created a systemd service file
sudo nano /etc/systemd/system/custom.service
<img width="407" height="263" alt="image" src="https://github.com/user-attachments/assets/4000bb16-d29c-4b74-8e5d-4335d3e2eb36" />

<img width="1140" height="838" alt="image" src="https://github.com/user-attachments/assets/6c15a674-c059-43a9-aeb9-b7beb735f124" />
**Explanation:**
[Unit]: Describes the service and its dependencies (After=network.target ensures it starts after networking).<br>
[Service]: Defines what to run (ExecStart) and restart policy.<br>
[Install]: Ensures it starts at normal runlevels (multi-user).<br>

___
- Reloaded systemd and start the service
```bash
sudo systemctl daemon-reload
sudo systemctl start custom.service
```

-------------
### ⚙️ 3. Enable Auto-Start on Boot

```bash
sudo systemctl enable custom.service
```

```bash
systemctl is-enabled custom.service*
```
To confirm <br>
<img width="645" height="63" alt="image" src="https://github.com/user-attachments/assets/55df1443-bd23-44b4-830f-47f7e0f365d0" />

------------
4. Stopped and Disabled Service (for cleanup)
<img width="1519" height="748" alt="image" src="https://github.com/user-attachments/assets/be719569-1c62-4414-a2eb-4c6352689a92" />

```bash
sudo systemctl stop custom.service
sudo systemctl disable custom.service
sudo rm /etc/systemd/system/custom.service
sudo systemctl daemon-reload
```

---------------------------------------
**Notes:**- 
- Systemd is a system and service manager for Linux that acts as the first process to start after the kernel boots. It is the default init system for many major Linux distributions and is responsible for initializing the system, managing user services, handling device management, logging, and network connections.

-------------
| Task | Command | Description |
|------|----------|-------------|
| View boot logs | `journalctl -b` | Shows logs from current boot |
| Check failed services | `systemctl --failed` | Lists services that failed to start |
| View specific service | `systemctl status <service>` | Shows status and recent logs |
| Create service file | `/etc/systemd/system/custom.service` | Defines new systemd unit |
| Reload systemd | `systemctl daemon-reload` | Reloads after config changes |
| Start service | `systemctl start custom.service` | Launches service manually |
| Enable autostart | `systemctl enable custom.service` | Starts at every boot |
| Stop/disable service | `systemctl stop custom.service` or `systemctl disable custom.service` | Manage service lifecycle |
