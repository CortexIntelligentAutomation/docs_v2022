---
title: "Try it out"
linkTitle: "Try it out"
description: "Information about trying out the Grafana Observability platform for the first time."
weight: 70
---

# {{< param title >}}

This guide describes how to try out a new Grafana observability platform to make sure it is working. Please ensure that the [Install Grafana][], [Install Loki][], [Install Promtail][] and [Setup Grafana][] steps have been completed before proceeding.

## Test Debugging Flows

Test the platform by creating a new flow and executing it using the following steps:

1. Click on the `Flows` charm, then the `+` button and click `Group` to open a dialog.
1. Enter a name for the group, configure the `Permission Groups` and click `OK` to create the group.

## Test Publishing Production Flows

1. Log in to Gateway with a user that has the `Admin` role.
1. Click on the `Settings` charm, then `Packages`.

## Test Executing Production Flows

1. The request should return a JSON object with the output variables of the flow e.g. `{ "Output": "2022-03-09T07:35:16+0000" }`.
1. Cortex Innovation has now been verified and is ready to use.

[Install Grafana]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallGrafana.MainDoc" >}}
[Install Loki]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.MainDoc" >}}
[Install Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.MainDoc" >}}
[Setup Grafana]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SetupGrafana" >}}
