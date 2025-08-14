System Resource Monitoring with Netdata (Task 7)

Overview
This project demonstrates how to monitor **real-time system resources** using **Netdata** running inside a Docker container.  
Netdata provides per-second visualizations for CPU, memory, disk, network, and container metrics via an interactive web dashboard.


      Task Goals
- Deploy Netdata using Docker.
- Access the Netdata dashboard in a browser.
- Capture real-time metrics for:
  - CPU usage
  - Memory usage
  - Disk usage
  - Docker container metrics (optional, if Docker socket mounted)
  - Explore system, modules, and directories panels.
  - Store proof screenshots in a GitHub repository.


Prerequisites
  Docker installed and running:
   [Download Docker Desktop](https://www.docker.com/products/docker-desktop/) for Windows/macOS.
   On Linux, install Docker Engine via package manager.
   Internet access to pull the Netdata image.


Setup & Run

Pull & Run Netdata
Run this command to start Netdata **with Docker socket access** so it can monitor containers:

```bash
docker run -d --name netdata \
  -p 19999:19999 \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  netdata/netdata
