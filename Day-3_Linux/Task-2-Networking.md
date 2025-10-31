# Task-2-Networking
## Debug real AWS networking issues from Linux.
1. Check instance IP, route table, and DNS.

```bash
# Show all network interfaces and IP addresses
ip addr show

# Or use the older (but still common) command
ifconfig

# View default route and routing table
ip route show

# Check DNS resolver configuration
cat /etc/resolv.conf
```
<img width="1255" height="540" alt="image" src="https://github.com/user-attachments/assets/879542f7-d326-48b9-8ee4-d5a1d15148f0" />

--------
2. Verify Internet Connectivity
```bash
# Check reachability to Google DNS
ping -c 4 8.8.8.8

# Check name resolution (DNS test)
ping -c 4 google.com

# Trace network path to an IP
traceroute google.com
```
<img width="939" height="460" alt="image" src="https://github.com/user-attachments/assets/275c5635-2d78-4c08-b47a-f46279041af3" />
<img width="934" height="387" alt="image" src="https://github.com/user-attachments/assets/38d49244-e917-43a5-b437-76f9faf58c84" />
<img width="1582" height="195" alt="image" src="https://github.com/user-attachments/assets/28599d01-7506-4916-90bf-82bebb6d11e6" />

---------
3. Open Firewall Ports for Custom Services
```bash
sudo netstat -tulnp | grep 8080
sudo ss -tuln
```
<img width="1647" height="592" alt="image" src="https://github.com/user-attachments/assets/58c79309-e2b3-454f-b597-095bd4bfcdf1" />

-----------
4. curl to Test Web Endpoints
```bash
# Simple connectivity test to a local or remote service
curl http://localhost:8080

# Verbose output to see headers and connection info
curl -v http://example.com

# Check HTTPS with certificate details
curl -Iv https://example.com
```
<img width="1173" height="484" alt="image" src="https://github.com/user-attachments/assets/3ca49f22-9b2a-42df-8cdc-88006fbc431a" />

----------


| Task | Command | Description |
|------|---------|-------------|
| View IPs & interfaces | `ip addr show` | Shows private/public IPs and network adapters |
| Check routes | `ip route show` | Displays default gateway and routing table |
| Check DNS | `cat /etc/resolv.conf` | Lists DNS servers in use |
| Test connectivity | `ping -c 4 8.8.8.8` | Verifies internet reachability |
| Test name resolution | `ping -c 4 google.com` | Checks DNS resolution |
| Open AWS port | `aws ec2 authorize-security-group-ingress ...` | Opens custom port in security group |
| Test service endpoint | `curl -v http://localhost:8080` | Verifies service response |

