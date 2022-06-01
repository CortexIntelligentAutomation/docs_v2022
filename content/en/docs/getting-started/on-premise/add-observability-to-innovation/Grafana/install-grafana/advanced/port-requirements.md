---
title: "Port Requirements for Web Application Server"
linkTitle: "Port Requirements for Web Application Server"
description: "Information about the ports opened when installing observability platform"
---

# {{< param title >}}

All the required ports for the Web Application Server in observability platform must be opened on Windows Firewall. These ports may be altered if another program overlaps with them.

## Observability Platform

| Name | Description | Default Port(s) | Protocol | Direction |
|------|-------------|-----------------|----------|-----------|
| Grafana | The port used by Grafana web application | 3000 | TCP | Inbound |
| Reverse proxy for Grafana Loki | The port used by IIS serving the role of a reverse proxy for the Grafana Loki | 2100 | TCP | Inbound |
