---
title: "Install Loki"
linkTitle: "Install Loki"
description: "Information about installing Grafana Loki on the Web Application Server."
weight: 10
---

# {{< param title >}}

This guide describes how to install Grafana Loki on the Web Application Server. Please ensure that the [Prerequisites][] have been completed before starting this installation.

## Install Grafana Loki

1. Download the Grafana Loki archive specified in [Software Requirements][]
1. Extract the archive content to a suitable location.
1. Download the [loki-local-config.yaml][] configuration file from Github observability repository and save it alongside the previously extracted Grafana Loki executable.
1. Download the [Grafana Loki Install.zip][] archive from ther Github observability repository and extract its content alongside the previously extracted Grafana Loki executable.
This archive contains [NSSM][] - the Non-Sucking Service Manager program and PowerShell scripts to help manage Grafana Loki as a service.
1. Run Windows PowerShell as Administrator
1. Change the location to where all the files were extracted to.
1. Execute the `.\Install-Loki.ps1` command to install the downloaded Grafana Loki executable as a service.
1. Execute the `.\Start-Loki.ps1` command to start the Grafana Loki service.

## Next Steps?

1. [Configure Loki][]

[Configure Loki]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.ConfigureLoki" >}}
[Grafana Loki Install.zip]: "\TODO"
[loki-local-config.yaml]: "\TODO"
[NSSM]: {{< url "NSSM.MainDoc" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
