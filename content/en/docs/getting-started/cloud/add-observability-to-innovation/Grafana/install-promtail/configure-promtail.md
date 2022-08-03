---
title: "Configure Promtail"
linkTitle: "Configure Promtail"
description: "Information about configuring Promtail on the Application Server(s)."
weight: 20
---

# {{< param title >}}

This guide describes how to configure Promtail on the Application Server(s).

{{% alert type="note" title="Note" %}}These steps must be performed for every Promtail installation in the cluster.{{% /alert %}}

## Configure Promtail

### Set Client URL for Grafana Loki

1. Open the `promtail-local-config.yaml` configuration file, which is located in the folder alongside the `promtail-windows-amd64.exe` file.
1. Set the Grafana Loki `URL` in the `clients` section.
TODO - Update for Cloud Loki
   The following template has been provided for convenience:
   `https://<username>:<password>@<loki host address>:<loki reverse proxy port>/loki/api/v1/push`
| Element | Description |
|------|-------------|
| username | The username of the user created during [Create Loki User][] steps. |
| password | The password which was set for the user  during [Create Loki User][] steps. |
| loki host address | The host address of the machine where the Grafana Loki reverse proxy was configured during [Add a New Website][] steps . This must match the configured host name. |
| loki reverse proxy port | The port of the Grafana Loki reverse proxy configured during [Add a New Website][] steps. Usually 2100. |

   A correct URL should be similar to `https://username:password@hostaddress:2100/loki/api/v1/push`.
1. Save the file.

### Set the positions.yaml File Path

1. Open the `promtail-local-config.yaml` configuration file, which is located in the folder alongside the `promtail-windows-amd64.exe` file.
1. Set the `filename` in the `positions` section to the location where you want the `positions.yaml` file to be created on Promtail startup.
1. Create all the folders of the path specified in the previous step.
1. Save the file.

{{% alert title="Note" %}}
If the specified path to the folder for the `positions.yaml` file doesn't exists, the file will not get created on Promtail startup.
{{% /alert %}}

### Set the Path to the Cortex API Gateway Service Log Files

1. Open the `promtail-local-config.yaml` configuration file, which is located in the folder alongside the `promtail-windows-amd64.exe` file.
1. Set the `__path__` in the `static_configs` > `targets` > `labels` section to the path of the `Logs` folder specified in the `appSettings.json` file during installation of the Cortex API Gateway Service, e.g. `"C:/ProgramData/Cortex/Cortex API Gateway Service/Logs/*.json"`.
1. Save the file.

### Start Promtail

1. Run Windows PowerShell as Administrator.
1. Change the location to the folder where the `promtail-windows-amd64.exe` file is located.
1. Execute the `.\Start-Promtail.ps1` command to start the Promtail Windows service.

## Next Steps?

1. [Import Dashboards][]

[Import Dashboards]: {{< url "Cortex.GettingStarted.Cloud.AddObservabilityToInnovation.Grafana.ImportDashboards.MainDoc" >}}
