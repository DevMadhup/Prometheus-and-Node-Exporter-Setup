# Download Linux tar.gz file from below:
### wget https://github.com/prometheus/prometheus/releases/download/v2.47.0/prometheus-2.47.0.linux-amd64.tar.gz

# Extract tar.gz file
### tar zxvf prometheus-2.47.0.linux-amd64.tar.gz

# Create a file under following path
### vi /etc/systemd/system/prometheus.service

# Add below lines inside node.service file
[Unit]

Description=Prometheus Server

Documentation=https://prometheus.io/docs/introduction/overview/

After=network-online.target

[Service]

User=root

Restart=on-failure

ExecStart=/home/ubuntu/prometheus-2.47.0.linux-amd64/prometheus --config.file=/home/ubuntu/prometheus-2.47.0.linux-amd64/prometheus.yml

[Install]

WantedBy=multi-user.target

# Daemon-reload
### systemctl daemon-reload

# Restart node exporter
### systemctl restart prometheus

### node exporter runs on 9090 port no.
