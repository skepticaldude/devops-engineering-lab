
# Backend API + Nginx Reverse Proxy (Practical)

It covers:  
- [Python API](https://github.com/skepticaldude/devops-learning/blob/main/Backend%20API%20+%20Nginx%20Reverse%20Proxy/README.md#python-api-server-code)  
- Running/testing  
- Nginx reverse proxy setup  
- Logs & explanation  
- [Key takeaways](https://github.com/skepticaldude/devops-learning/tree/main/Backend%20API%20%2B%20Nginx%20Reverse%20Proxy#key-takeaways) & [real-world relevance](https://github.com/skepticaldude/devops-learning/blob/main/Backend%20API%20+%20Nginx%20Reverse%20Proxy/README.md#real-world-relevance)  

## Objective
Simulate a real-world backend system by building a local API and connecting it to Nginx using a reverse proxy.

---

## What Was Built

- A Python-based backend API server running on **port 5000**
- API returns **JSON responses** (no UI)
- Multiple endpoints:
  - `/` → server status
  - `/time` → current system time
- Nginx configured as a **reverse proxy** on **port 80**

---

## Architecture

```

Client (curl/browser)
↓
Nginx (port 80)
↓
Backend API (port 5000)
↓
JSON Response

````

---

## Key Concepts Learned

- **Backend API**: A server that returns data (JSON) instead of HTML  
- **HTTP Requests**:
  - `GET /` → fetch data from server  
- **Ports**:
  - 80 → Nginx (public entry point)  
  - 5000 → API (internal service)  
- **Reverse Proxy**: Nginx forwards requests to the backend server  

---

## Python API Server Code

Create `api_server.py` in your WSL home directory:

```python
from http.server import BaseHTTPRequestHandler, HTTPServer
import json

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        if self.path == "/":
            response = {
                "status": "ok",
                "message": "server is running"
            }
        elif self.path == "/time":
            import datetime
            response = {
                "current_time": str(datetime.datetime.now())
            }
        else:
            response = {
                "error": "not found"
            }

        self.send_response(200)
        self.send_header("Content-type", "application/json")
        self.end_headers()
        self.wfile.write(json.dumps(response).encode())

server = HTTPServer(("0.0.0.0", 5000), MyHandler)
print("Server running on port 5000...")
server.serve_forever()
````

---

## Run the API Server

```bash
python3 ~/api_server.py
```

**Expected Output in Terminal:**

```
Server running on port 5000...
```

---

## Test API with curl

### Root endpoint

```bash
curl http://localhost:5000
```

**Expected JSON output:**

```json
{"status": "ok", "message": "server is running"}
```

### Time endpoint

```bash
curl http://localhost:5000/time
```

**Expected JSON output:**

```json
{"current_time": "2026-03-21 16:15:30.123456"}
```

---

## Nginx Configuration Update

Open Nginx default site config:

```bash
sudo nano /etc/nginx/sites-available/default
```

Replace the default block:

```nginx
location / {
    try_files $uri $uri/ =404;
}
```

With:

```nginx
location / {
    proxy_pass http://127.0.0.1:5000;
}
```

Save and exit.

---

## Restart Nginx

```bash
sudo service nginx restart
```

---

## Test Reverse Proxy

```bash
curl http://localhost
```

**Expected Output:**

```json
{"status": "ok", "message": "server is running"}
```

> Now Nginx is forwarding requests to your API server.

---

## Observations (Logs)

* Backend logs show something like:

```
127.0.0.1 - - [21/Mar/2026 16:15:30] "GET / HTTP/1.0" 200
```

**Meaning:**

* `127.0.0.1` → request came from localhost
* `GET /` → endpoint accessed
* `200` → success

---

## Key Takeaways

* Built a working backend API system
* Learned **request → response lifecycle**
* Configured **Nginx as a reverse proxy**
* Observed **real server logs** showing traffic

---

## Real-World Relevance

* Mirrors production systems:

  * Nginx handles incoming traffic
  * Backend APIs process requests
  * Clients (web/mobile apps) consume JSON

---

## Next Steps

* Add more API endpoints (`/health`, `/users`)
* Implement monitoring/logging automation
* Deploy to a cloud VM for persistent access
* Introduce Infrastructure as Code (IaC)

