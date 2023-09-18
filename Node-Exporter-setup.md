# Download Linux tar.gz file from below:
### wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz

# Extract tar.gz file
### tar zxvf node_exporter-1.6.1.linux-amd64.tar.gz

# Create a file under following path
### vi /etc/systemd/system/node.service

# Add below lines inside node.service file
[Unit]

Description=Node Exporter

Documentation=https://prometheus.io/docs/introduction/overview/

After=network-online.target

[Service]

User=root

Restart=on-failure

ExecStart=/home/ubuntu/node_exporter-1.6.1.linux-amd64/node_exporter

[Install]

WantedBy=multi-user.target

# Daemon-reload
### systemctl daemon-reload

# Restart node exporter
### systemctl restart node

### node exporter runs on 9100 port no.
