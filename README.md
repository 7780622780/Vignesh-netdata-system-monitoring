System Resource Monitoring with Netdata (Task 7)

**Overview**
This repository contains the setup and exploration of **Netdata** for real-time system resource monitoring.  
Netdata was deployed inside a Docker container and accessed via a browser to visualize **CPU**, **Memory**, **Disk**, **Network**, and (optionally) **Docker container** metrics.  

---

 **Objectives**
- Deploy **Netdata** using Docker.
- Access the Netdata dashboard in a browser.
- Capture **real-time charts** for CPU, Memory, Disk.
- Explore **System**, **Modules**, **Directories**, and **Logs**.
- (Optional) Capture **Docker/Containers** section by mounting Docker socket.

---

**Prerequisites**
- **Docker** installed and running.
- **Port 19999** available.
- Internet access to pull the `netdata/netdata` image.

---

Setup Steps

Run Netdata (Basic)
```bash
docker run -d --name netdata -p 19999:19999 netdata/netdata

Run Netdata with Docker Socket Access (for container metrics)
docker rm -f netdata
docker run -d --name netdata \
  -p 19999:19999 \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  netdata/netdata
