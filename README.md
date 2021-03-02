# CDEM Logger

Simple script to log output of a CDEM device to log file. Can for example be run on a Raspberry Pi.

## Systemd Service

Create unit file:

```bash
sudo nano /lib/systemd/system/cdem_logger.service
```

Add the following (make sure to adjust path):

```text
[Unit]
Description=CDEM Logger
After=multi-user.target

[Service]
Type=idle
ExecStart=/home/pi/cdem-logger/logger >> /home/pi/cdem_log 2>&1

[Install]
WantedBy=multi-user.target
```

Set correct permissions:

```bash
sudo chmod 644 /lib/systemd/system/cdem_logger.service
```

Activate unit

```bash
sudo systemctl daemon-reload
sudo systemctl enable cdem_logger.service
```

Reboot

```bash
sudo reboot
```
