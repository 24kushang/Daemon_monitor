# Daemon Monitor
The focus of this project is to monitor the docker daemon using Prometheus. Following the references from Docker documentation, the project scrapes the metrics from the daemon.

Steps to clone the repository
---
1. Clone the repository by following the git command:
   
   ```bash
    git clone <HTTP/SSH>
   ```
3. We need to turn on the internal daemon statistics provider to be turned on.
   * Enter Docker Desktop settings at  `Settings > Docker Engine`
   * Linux: `/etc/docker/daemon.json`
   * Windows Server: `C:\ProgramData\docker\config\daemon.json`
   
     ```json
     "metrics-addr": "127.0.0.1:9323"
     ```
4. Turning up the docker-compose using the command
   
   ```bash
   docker compose up
   ```
|Note: Here the Daemon metrics are exposed at `127.0.0.1:9232` and Prometheus has `9091:9090` port-mapping so as not to affect the default Prometheus running in the system.

---

Open to any suggestions to scrape docker daemon
