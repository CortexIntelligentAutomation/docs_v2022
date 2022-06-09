---
name: "Configure Loki"
linkTitle: "Configure Loki"
description: "Information about Configuring Grafana Loki on the Web Application Server."
weight: 20
---

# {{< param name >}}

This guide describes how to configure Grafana Loki on the Web Application Server.

{{% alert type="note" title="Note" %}}For security reasons Grafana Loki should be run behind an encrypted and authenticated reverse proxy as it does not provide theses features by itself.{{% /alert %}}

## Setup Reverse Proxy with IIS

All of the steps must be carried out on the Web Application Server.

### Install IIS Basic Authentication

1. Run *Server Manager*.
1. Expand the *Manage* menu and select *Add Roles and Features*.
1. In the left-hand menu select *Server Selection*.
1. Select the name of the Web Application Server, click *Next*.
1. On the *Server Roles* page, in the *Roles* tree expand *Web Server (IIS)* --> *Web Server* --> *Security*.
1. Select *Basic Authentication*, click *Next*.
1. Click *Next* to get to the *Confirm installation selections* page.
1. Click *Install*.
1. Click *Close* on the *Results* page.

### Install IIS URL Rewrite Module

1. Download the URL Rewrite module specified in [Software Requirements][]
1. 

### Set Up Reverse Proxy

To set up a reverse proxy carry out the following configuration.

### Configure HTTPS

To encrypt communication between clients and the reverse proxy carry out the following configuration.

1. Run a text editor in administrator mode.

### Configure Authentication

To provide authentication for the reverse proxy carry out the following configuration.

## Next Steps?

1. [Install Promtail][]

[Install Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.MainDoc" >}}
