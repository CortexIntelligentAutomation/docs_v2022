---
name: "Try it out"
linkTitle: "Try it out"
description: "Information about trying out the Grafana Observability platform for the first time."
weight: 70
---

# {{< param name >}}

This guide describes how to try out a new Grafana observability platform to make sure it is working. Please ensure that the [Install Grafana][], [Install Loki][], [Install Promtail][] and [Setup Grafana][] steps have been completed before proceeding.

## Verify That HTTPS Works

It is important to verify that Grafana is only accessible though HTTPS and not HTTP connection.

1. On the Web Application Server open a web browser.
1. Browse to `http://localhost:3000/`.
1. Browser should not be able to make a connection to Grafana and a default error page should be displayed.
1. Browse to `https://localhost:3000/`.
1. On the login page, enter `admin` and the corresponding password.
1. Click Log in.
1. You should have successfully logged into Grafana.

[Install Grafana]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallGrafana.MainDoc" >}}
[Install Loki]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.MainDoc" >}}
[Install Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.MainDoc" >}}
[Setup Grafana]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SetupGrafana" >}}
