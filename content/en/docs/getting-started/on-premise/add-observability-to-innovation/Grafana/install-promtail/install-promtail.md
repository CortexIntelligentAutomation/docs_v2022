---
title: "Install Promtail"
linkTitle: "Install Promtail"
description: "Information about installing Promtail on the Application Server(s)."
weight: 10
---

# {{< param title >}}

This guide describes how to install Promtail on the Application Server(s). Please ensure that the [Prerequisites][] have been completed before starting this installation.

## Install Promtail

1. Download [Promtail 2.5.0 (promtail-windows-amd64.exe.zip)][].
1. Extract the archive content to a suitable location.
1. Navigate to the observability repository in [GitHub][Download Promtail Yaml].
1. Click on the `promtail-local-config.yaml` file.
1. Copy the contents and save locally as `promtail-local-config.yaml` in the same location as the previously extracted `promtail-windows-amd64.exe`.
1. Using the browser back button, go back up a level to the file list.
1. Download the [Promtail Install.zip][] archive and extract its content alongside the previously extracted `promtail-windows-amd64.exe`.
This archive contains [NSSM][] - the Non-Sucking Service Manager program and PowerShell scripts to help manage Promtail as a service.
1. Run Windows PowerShell as Administrator
1. Change the location to where all the files were extracted to.
1. Execute the `.\Install-Promtail.ps1` command to install the downloaded `promtail-windows-amd64.exe` as a service.

## Next Steps?

1. [Configure Promtail][]

[Configure Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.ConfigurePromtail" >}}
[Download Promtail Yaml]: {{< url "GitHub.Cortex.Observability.PromtailYaml" >}}
[NSSM]: {{< url "NSSM.MainDoc" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
[Promtail 2.5.0 (promtail-windows-amd64.exe.zip)]:  {{< url "Grafana.SelfManaged.Downloads.GrafanaLoki.MainDoc" >}}
[Promtail Install.zip]: {{< url "GitHub.Cortex.Observability.PromtailInstallZip" >}}
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
