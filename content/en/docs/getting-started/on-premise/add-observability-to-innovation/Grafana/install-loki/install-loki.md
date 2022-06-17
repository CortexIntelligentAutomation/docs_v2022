---
title: "Install Loki"
linkTitle: "Install Loki"
description: "Information about installing Grafana Loki on the Web Application Server."
weight: 10
---

# {{< param title >}}

This guide describes how to install Grafana Loki on the Web Application Server. Please ensure that the [Prerequisites][] have been completed before starting this installation.

## Install Grafana Loki

1. Download the [Grafana Loki 2.5.0 (loki-windows-amd64.exe.zip)][]
1. Extract the archive content to a suitable location.
1. Navigate to the observability repository in [GitHub][Download Loki Yaml].
1. Click on the `loki-local-config.yaml` file.
1. Copy the contents and save locally as `loki-local-config.yaml` in the same location as the previously extracted Grafana Loki `loki-windows-amd64.exe`.
1. Download the [Grafana Loki Install.zip][] archive and extract its contents alongside the previously extracted Grafana Loki `loki-windows-amd64.exe`.
This archive contains [NSSM][] - the Non-Sucking Service Manager program and PowerShell scripts to help manage Grafana Loki as a Windows service.
1. Run Windows PowerShell as Administrator
1. Change the location to where all the files were extracted to.
1. Execute the `.\Install-Loki.ps1` command to install the downloaded Grafana Loki `loki-windows-amd64.exe` as a service.
1. Execute the `.\Start-Loki.ps1` command to start the Grafana Loki service.

## Next Steps?

1. [Configure Loki][]

[Configure Loki]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.ConfigureLoki" >}}
[Download Loki Yaml]: {{< url "GitHub.Cortex.Observability.LokiYaml" >}}
[Grafana Loki 2.5.0 (loki-windows-amd64.exe.zip)]: {{< url "Grafana.SelfManaged.Downloads.GrafanaLoki.MainDoc" >}}
[Grafana Loki Install.zip]: {{< url "GitHub.Cortex.Observability.LokiInstallZip" >}}
[NSSM]: {{< url "NSSM.MainDoc" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
