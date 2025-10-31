# Task-3-System_Monitoring_Troubleshooting.md

---

### Tasks
1. Check CPU, memory, and disk usage.  
2. Find top resource-consuming processes.  
3. Analyze logs and system health.

---

### Ubuntu Commands

```bash
# View real-time CPU and memory usage
top

# Interactive process viewer (more visual)
htop
<img width="1640" height="599" alt="image" src="https://github.com/user-attachments/assets/4352a737-3ddc-44d7-b544-d7b098413b73" />

# Check memory usage
free -h

# Check disk usage per filesystem
df -h

# Check disk usage per folder
du -sh /var/*

# List processes sorted by memory usage
ps aux --sort=-%mem | head

# View detailed system logs
sudo journalctl -xe

# View kernel messages (last few lines)
sudo dmesg | tail
```
<img width="649" height="480" alt="image" src="https://github.com/user-attachments/assets/e0e6e5b6-fd4b-4723-98cf-82c0322b7602" />
