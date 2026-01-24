# Docker Dozzle Stack

## Open Port in UFW for Node-Exporter

We need to create a UFW application so that we can let vmagent scrape Node-Exporter

```bash
sudo vi /etc/ufw/applications.d/dozzle
```

```bash
[Dozzle]
title=Dozzle
description=Allows incoming traffic for Dozzle on port 7007
ports=7007/tcp
```

We then can enable this new application

```bash
sudo ufw app update Dozzle
sudo ufw app list
sudo ufw allow Dozzle
```