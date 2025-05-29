INSTALL.md - Manual Setup for TICK Stack with Docker

This guide explains how to manually install and run the TICK stack (Telegraf, InfluxDB, Chronograf/Grafana, Kapacitor) using Docker and Docker Compose.

✅ 1. Install Docker

sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker

✅ 2. Install Docker Compose

sudo apt install -y docker-compose

✅ 3. Create Project Directory

Choose a folder (recommended: /opt/dockers-installation) and set the right permissions:

sudo mkdir -p /opt/dockers-installation
sudo chown $USER:$USER /opt/dockers-installation
cd /opt/dockers-installation

✅ 4. Place Required Files

Ensure these files and folders exist inside the project directory:

/opt/dockers-installation/
├── docker-compose.yml
├── telegraf/
│   └── telegraf.conf

If you have a ZIP file (e.g. tick-stack-docker.zip), extract it:

unzip tick-stack-docker.zip
cd tick-stack-docker

✅ 5. Start the Stack

Navigate to the folder that contains docker-compose.yml and run:

docker-compose up -d

This will start the following containers:

InfluxDB (Port 8086)

Telegraf (collects metrics)

Kapacitor (alerting engine)

Grafana (Port 3000, for dashboards)

🔎 6. Verify Running Containers

docker ps

You should see the 4 containers listed and running.

🖥 7. Access Grafana Web UI

Open your browser:

http://localhost:3000

Login:

Username: admin

Password: admin

Add InfluxDB as a data source:

URL: http://influxdb:8086

Database: telegraf

📬 Need Help?

This setup assumes:

You are on an Ubuntu machine

Docker and Docker Compose are correctly installed

Ports 3000 (Grafana), 8086 (InfluxDB), and 9092 (Kapacitor) are free

For issues, check logs:

docker-compose logs

Author: ZdravecRepo: https://github.com/ZdravecPanov/dockers-installation
