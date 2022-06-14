---
title: "Configure Promtail"
linkTitle: "Configure Promtail"
description: "Information about Configuring Promtail on the Application Server(s)."
weight: 20
---

# {{< param title >}}

This guide describes how to configure Promtail.

{{% alert type="note" title="Note" %}}These steps must be performed for every Promtail installation in the cluster.{{% /alert %}}

## Configure Promtail

1. Open the `promtail-local-config.yaml` configuration file which is located in the folder alongside the Promtail executable.
1. Set the Grafana Loki `url` in the `clients` section. The following template has been provided for convinience: 
`https://{username}:{password}@{Loki Host}:{Loki Reverse Proxy Port}/loki/api/v1/push`
| Element | Description |
|------|-------------|
| username | The username of the user created during [Create Loki User][] steps |
| password | The password which was set for the user  during [Create Loki User][] steps |
| Loki Host | The host address of the machine where reverse proxy was configured during [Add a New Website][] steps |
| Loki Reverse Proxy Port | The port of the Grafana Loki reverse proxy configured during [Add a New Website][] steps. Usually 2100. |

   A corect url should be similar to `https://username:password@hostname:2100/loki/api/v1/push`.

## Start Promtail

1. Run Windows PowerShell as Administrator
1. Change the location to where the Promtail executable is located.
1. Execute the `.\Start-Promtail.ps1` command to start the Grafana Loki service.

## Next Steps?

1. [Configure Promtail][]

[Add a New Website]: {Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.AddANewWebsite}
[Create Loki User]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.CreateLokiUser" >}}
[Configure Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.ConfigurePromtail" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
[Promtail Install.zip]: "TODO"
[promtail-local-config.yaml]: "TODO"
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
