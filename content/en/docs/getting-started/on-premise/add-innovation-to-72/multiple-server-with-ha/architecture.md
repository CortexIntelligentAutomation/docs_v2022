---
title: "Architecture"
linkTitle: "Architecture"
description: "Information about the recommended platform architecture, including component descriptions."
weight: 10
---

# {{< param title >}}

## Components

| Component                                         | Purpose                                                                             | Required/Optional           | Server Role                                |
|---------------------------------------------------|-------------------------------------------------------------------------------------|-----------------------------|--------------------------------------------|
| [Cortex Gateway][Gateway Guide]                   | {{< commonSection "/headless/component-purpose/cortex-gateway.md" >}}               | Required                    | Web Application Server                     |
| [Cortex Studio][Studio Guide]                     | {{< commonSection "/headless/component-purpose/cortex-studio.md" >}}                | Required                    | Web Application Server                     |
| Cortex Flow Debugger Service                      | {{< commonSection "/headless/component-purpose/cortex-flow-debugger-service.md" >}} | Required                    | Web Application Server                     |
| Cortex API Gateway Service                        | {{< commonSection "/headless/component-purpose/cortex-api-gateway-service.md" >}}   | Required                    | Application Server                         |
| Cortex Execution Service                          | {{< commonSection "/headless/component-purpose/cortex-execution-service.md" >}}     | Required                    | Application Server                         |
| Cortex Block Packages                             | {{< commonSection "/headless/component-purpose/cortex-block-packages.md" >}}        | Required                    | Web Application Server, Application Server |
| Cortex Gateway Databases                          | {{< commonSection "/headless/component-purpose/cortex-gateway-databases.md" >}}     | Required<br />(End of life) | Web Application Server                     |
| [SQL Server Express][] or [SQL Server Standard][] | {{< commonSection "/headless/component-purpose/ms-sql-server.md" >}}                | Required<br />(End of life) | Web Application Server                     |
| [Microsoft Service Fabric][]                      | {{< commonSection "/headless/component-purpose/ms-service-fabric.md" >}}            | Required                    | Application Server                         |
| [Microsoft Service Fabric Explorer][]             | {{< commonSection "/headless/component-purpose/ms-service-fabric-explorer.md" >}}   | Required                    | Application Server                         |
| [Particular NServiceBus][]                        | {{< commonSection "/headless/component-purpose/particular-nservicebus.md" >}}       | Required                    | Application Server                         |
| [Pivotal RabbitMQ][]                              | {{< commonSection "/headless/component-purpose/pivotal-rabbitmq.md" >}}             | Required                    | Application Server                         |
| [Erlang OTP][]                                    | {{< commonSection "/headless/component-purpose/erlang-otp.md" >}}                   | Required                    | Application Server                         |
| [gobetween][]                                     | {{< commonSection "/headless/component-purpose/gobetween.md" >}}                    | Required                    | Load Balancer                              |
| [NSSM][]                                          | {{< commonSection "/headless/component-purpose/nssm.md" >}}                         | Required                    | Load Balancer                              |

{{% alert title="Note" %}}
Cortex v7.2 component descriptions are not covered in this guide. See separate v7.2 documentation for more information.
{{% /alert %}}

## Possible Architectures

Cortex Innovation and v7.2 can run side-by-side, allowing flows to be built and run for both of them from the same Gateway instance. They each require a different set of back-end components to be installed. Innovation can be added to a v7.2 installation by using the existing hardware containing v7.2 components, using new hardware or a combination of the two. The only components shared by both Innovation and v7.2 are Gateway and its databases.

The installation process is the same, regardless of which architecture is used; [Recommended][], [Minimum][] or [Alternative][]. The only difference is the [Hardware Requirements][], which will be greater for existing machines as they need more resources to run more components.

### Recommended Architecture

The recommended architecture for adding Innovation to a v7.2 Dual Site, Dual Server system requires 8 servers in total; the 4 existing servers, plus 4 new servers:

* 2x Existing Application Servers for v7.2, one of these will also act as the Web Application Server for Innovation. For Innovation, the existing Gateway will be upgraded and a new Flow Debugger Service will be added.
* 2x Existing Database Servers, used for v7.2 and Gateway databases.
* 1x New Load Balancer Server for Innovation.
* 3x New Application Servers for Innovation.

{{< figure src="/images/editable/Cortex Innovation and v7.2 Best Architecture.png" class="centre" title="8 Server, Recommended Architecture Diagram" >}}.

### Minimum Architecture

The minimum architecture requires only the 4 existing servers:

* 2x Application Servers for v7.2, each of these will also host one of the three Application Servers for Innovation.
* 1x Database Server for v7.2, which will also host the remaining Application Server for Innovation.
* 1x Database Server for v7.2, which will also host the Load Balancer for Innovation.

{{< figure src="/images/editable/Cortex Innovation and v7.2 Min Architecture.png" class="centre" title="4 Server, Minimum Architecture Diagram" >}}.

### Alternative Architectures

Alternative architectures are possible; any of the Innovation server roles may be installed on any of the existing or new servers provided that the hardware is capable of running everything according to the [Hardware Requirements for Alternative Architectures][]. For example, if the database servers cannot have anything else installed on them, new servers may be used for the load balancer and the third Innovation Application Server. Additionally, an existing, alternative load balancer may be used instead of the bundled one. The only caveat is that the load balancer must not be installed on the same machine as an Innovation Application Server as it cannot be used to send traffic to itself.

## Next Steps?

1. [Prerequisites][]

[Gateway Guide]: {{< url "Cortex.Guides.Gateway.MainDoc" >}}
[Studio Guide]: {{< url "Cortex.Guides.Studio.MainDoc" >}}
[Prerequisites]: {{< url "Cortex.GettingStarted.OnPremise.AddInnovationTo72.MultipleServerWithHA.Prerequisites" >}}
[Hardware Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddInnovationTo72.MultipleServerWithHA.HardwareRequirements" >}}
[Hardware Requirements for Alternative Architectures]: {{< url "Cortex.GettingStarted.OnPremise.AddInnovationTo72.MultipleServerWithHA.HardwareRequirementsAlternativeArchitecture" >}}
[SQL Server Express]: {{< url "MSDownload.SqlServerExpress.2016" >}}
[SQL Server Standard]: {{< url "MSEval.SQLServer.2019" >}}
[Microsoft Service Fabric]: {{< url "MSDocs.ServiceFabric.MainDoc" >}}
[Microsoft Service Fabric Explorer]: {{< url "MSDocs.ServiceFabric.Explorer" >}}
[Particular NServiceBus]: {{< url "Particular.NServiceBus.MainDoc" >}}
[Pivotal RabbitMQ]: {{< url "RabbitMQ.MainDoc" >}}
[Erlang OTP]: {{< url "ErlangOTP.MainDoc" >}}
[gobetween]: {{< url "GoBetween.MainDoc" >}}
[NSSM]: {{< url "NSSM.MainDoc" >}}
[Recommended]: {{< ref "#recommended-architecture" >}}
[Minimum]: {{< ref "#minimum-architecture" >}}
[Alternative]: {{< ref "#alternative-architectures" >}}
