## How to setup node exporter setup on linux machine 
- Download Linux tar.gz file from below:
  
```bash
wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz
```
#
- Extract tar.gz file
  
```bash
tar zxvf node_exporter-1.6.1.linux-amd64.tar.gz
```
#
- Create a file under following path
  
```bash
vi /etc/systemd/system/node.service
```
# 
- Add below lines inside node.service file
  
```bash
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
```
#
- Daemon-reload
  
```bash
systemctl daemon-reload
```
#
- Restart node exporter

```bash
systemctl restart node
```
#
> [!Important]
> node exporter runs on 9100 port no.

