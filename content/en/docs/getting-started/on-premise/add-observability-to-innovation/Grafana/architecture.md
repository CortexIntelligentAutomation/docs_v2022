---
title: "Architecture"
linkTitle: "Architecture"
description: "Information about the recommended architecture for a Grafana platform installation."
weight: 10
---

# {{< param title >}}

## Components

| Component | Purpose | Required/Optional |Server Role |
|-----------|---------|----------|------------|
| Grafana| Web application that provides querying and visualisation of data in the form of dashboards. | Required | Web&nbsp;Application&nbsp;Server |
| Grafana Loki | Log aggregation system designed to store and query logs from applications and infrastructure. | Required | Web&nbsp;Application&nbsp;Server |
| Promtail | An agent which ships the contents of local logs to a Grafana Loki instance. It should be deployed to every machine that has a Microsoft Service Fabric Node used by Innovation. | Required | Application&nbsp;Server |
| Microsoft&nbsp;Internet&nbsp;Information&nbsp;Services&nbsp;(IIS) | Web server for hosting websites, services, and applications. | Required | Web&nbsp;Application&nbsp;Server |

## Recommended Architecture

The following architecture requires 1 + 1..n servers:

* 1 x Web Application Server which contains Grafana, Grafana Loki and Microsoft IIS.
* 1..n x Application Servers

{{< figure src="/images/Grafana Platform Architecture Diagram.png" title="Grafana Platform Architecture Diagram" >}}

## Next Steps?

1. [Prerequisites][]

[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Prerequisites" >}}
