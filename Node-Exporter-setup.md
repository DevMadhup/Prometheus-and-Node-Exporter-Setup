## How to setup node exporter setup on linux machine 

- Download the linux tar.gz file using the below command:
  
```bash
wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz
```
#
- Extract the node exporter tar.gz file
  
```bash
tar zxvf node_exporter-1.6.1.linux-amd64.tar.gz
```
#
- Create a file node.service inside the <mark>/etc/systemd/system</mark> directory.
  
```bash
vi /etc/systemd/system/node.service
```
# 
- Now, open the node.service file and paste the below content.
  
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
- Reload the system daemon
  
```bash
systemctl daemon-reload
```
#
- Restart the node exporter

```bash
systemctl restart node
```
#
> [!Important]
> node exporter runs on 9100 port no.

