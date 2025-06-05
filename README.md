#  Task 7: Monitor System Resources Using Netdata

## Objective
Install and use Netdata via Docker to monitor real-time system and container performance.

## Tools Used
- Docker
- Netdata (https://github.com/netdata/netdata)

## Steps to Run

**Step 1: Pull & Run Netdata Container**

Open your terminal or command prompt and run the following Docker command:

>> docker run -d --name=netdata -p 19999:19999 --cap-add=SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata


This command will:
- Pull the official Netdata image
- Expose the dashboard on port 19999
- Allow system-level monitoring using required capabilities
  
# Step 2: Open Netdata Dashboard

Go to your browser and open:

http://localhost:19999

You will see a real-time dashboard showing:
- CPU usage
- RAM consumption
- Disk I/O
- Network activity
- Docker container stats (if Docker is installed)

**Step 3: Explore Dashboard Features**

- System metrics: CPU, RAM, Swap, Disks
- Docker containers: CPU/memory per container
- Alerts: Warnings/critical metrics
- Charts: Click on each for details over time

# Step 4: Check Logs (Optional)

To view logs (from inside the container):

>> docker exec -it netdata bash

>> cd /var/log/netdata

>> ls

>> cat error.log

