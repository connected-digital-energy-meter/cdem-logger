# CDEM Logger

Simple script to log output of a CDEM device to log file. Can for example be run on a Raspberry Pi.

## Systemd Service

Copy unit file:

```bash
sudo cp ./cdem_logger.service /lib/systemd/system/
```

Change the path to the `logger` if needed.

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
