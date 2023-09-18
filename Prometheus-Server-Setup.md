

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
