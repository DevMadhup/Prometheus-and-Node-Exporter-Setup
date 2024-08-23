## How to setup prometheus on linux machine

- Download Linux tar.gz file using the below command:

```bash
wget https://github.com/prometheus/prometheus/releases/download/v2.47.0/prometheus-2.47.0.linux-amd64.tar.gz
```
#
- Extract tar.gz file

```bash
tar zxvf prometheus-2.47.0.linux-amd64.tar.gz
```
# 
- Create a prometheus.service inside the <mark>/etc/systemd/system</mark> directory

```bash
vi /etc/systemd/system/prometheus.service
```
#
- Now, open the prometheus.service file and paste the below content

```bash
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
```
# 
- Reload the system daemon

```bash
systemctl daemon-reload
```
#
- Restart the prometheus server

```bash
systemctl restart prometheus
```
#
> [!Important]
> node exporter runs on 9090 port no.

#
> [!Important]
> If you want to get the logs from the node, follow the below step:

- Finally, Add below line in prometheus.yml file under <mark>targets: ["localhost:9000"]</mark> line
```bash
- targets: ["<public_ip_of_node-exporter-server>:9100"]
```
# 
- Reload the system daemon

```bash
systemctl daemon-reload
```
#
- Restart the prometheus server

```bash
systemctl restart prometheus
```
#
