# WSL First Server Project (Windows Subsystem for Linux) 

## Lesson Summary: Cloud/Infra Fundamentals (Date: 21 March 2026)

### Goal
Set up a local web server on WSL, understand ports, HTTP requests, and automation with cron jobs.

---

### Topics Covered

1. **WSL Environment**
   - Verified Linux distro (`Docker Desktop` detected; Ubuntu recommended for full features)
   - Understanding minimal environments vs full Ubuntu WSL

2. **Nginx Web Server**
   - Installed and started Nginx on WSL
   - Verified server listening on port 80
   - Tested with:
     ```bash
     curl http://localhost
     ```
   - Served a custom HTML page:
     ```html
     <h1>My First Server</h1>
     <p>Cloud Engineer in Training 🚀</p>
     ```

3. **Networking Concepts**
   - Ports: Port 80 = HTTP requests  
   - HTTP request/response cycle (GET requests)
   - Localhost testing → browser interaction  
   - Accessing from local network (future step with Wi-Fi or tunneling)

4. **Cron Jobs (Automation)**
   - Created first cron job to run every minute:
     ```cron
     * * * * * echo "Server still alive at $(date)" >> ~/server_status.log
     ```
   - Verified log file updates:
     ```bash
     cat ~/server_status.log
     ```
   - Concepts learned:
     - Scheduled automation
     - Minimal CPU/RAM/disk usage
     - Dependence on OS being active

---

### Key Takeaways

- Servers must run to respond to requests; cron jobs need the OS active  
- Local testing is sufficient for understanding infra fundamentals  
- WSL + Nginx + cron = foundation for cloud & backend skills  
- Small, lightweight tasks teach automation without heavy resource usage  

---

### Optional Extensions

- Simulate a backend API with JSON responses  
- Combine cron jobs with server monitoring  
- Deploy the server on a cloud VM for persistent “always-on” behavior  
- Use tunneling tools (ngrok/localtunnel) for external access

---

### Commands Used (Optional `commands.sh`)

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Nginx
sudo apt install nginx -y

# Start Nginx server
sudo service nginx start

# Test server
curl http://localhost

# Edit webpage
sudo nano /var/www/html/index.html

# Cron job example
crontab -e
# Add: * * * * * echo "Server still alive at $(date)" >> ~/server_status.log
