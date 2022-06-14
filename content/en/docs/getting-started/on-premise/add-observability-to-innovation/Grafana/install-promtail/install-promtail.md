---
title: "Install Promtail"
linkTitle: "Install Promtail"
description: "Information about installing Promtail on the Application Server(s)."
weight: 10
---

# {{< param title >}}

This guide describes how to install Promtail on the Application Server(s). Please ensure that the [Prerequisites][] have been read before starting this installation.

## Install Promtail

1. Download the Promtail archive specified in [Software Requirements][]
1. Extract the archive content to a suitable location.
1. Download the [promtail-local-config.yaml][] configuration file from Github observability repository and save it alongside the previously extracted Promtail executable.
1. Download the [Promtail Install.zip][] archive from ther Github observability repository and extract its content alongside the previously extracted Promtail executable.
This archive contains [NSSM][] - the Non-Sucking Service Manager program and PowerShell scripts to help manage Grafana Loki as a service.
1. Run Windows PowerShell as Administrator
1. Change the location to where all the files were extracted to.
1. Execute the `.\Install-Promtail.ps1` command to install the downloaded Grafana Loki executable as a service.

## Next Steps?

1. [Configure Promtail][]

[Configure Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.ConfigurePromtail" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
[Promtail Install.zip]: "TODO"
[promtail-local-config.yaml]: "TODO"
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
