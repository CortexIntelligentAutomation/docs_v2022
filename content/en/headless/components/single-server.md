| Component                                         | Purpose                                                                              | Required/Optional           | Server Role                                |
|---------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------|--------------------------------------------|
| [Cortex Gateway][Gateway Guide]                   | {{< commonSection "/headless/components/purpose/cortex-gateway.md" >}}               | Required                    | Web Application Server                     |
| [Cortex Studio][Studio Guide]                     | {{< commonSection "/headless/components/purpose/cortex-studio.md" >}}                | Required                    | Web Application Server                     |
| Cortex Flow Debugger Service                      | {{< commonSection "/headless/components/purpose/cortex-flow-debugger-service.md" >}} | Required                    | Web Application Server                     |
| Cortex API Gateway Service                        | {{< commonSection "/headless/components/purpose/cortex-api-gateway-service.md" >}}   | Required                    | Application Server                         |
| Cortex Execution Service                          | {{< commonSection "/headless/components/purpose/cortex-execution-service.md" >}}     | Required                    | Application Server                         |
| Cortex Packaging Service                          | {{< commonSection "/headless/components/purpose/cortex-packaging-service.md" >}}     | Required                    | Application Server                         |
| Cortex Provisioning Service                       | {{< commonSection "/headless/components/purpose/cortex-provisioning-service.md" >}}  | Required                    | Application Server                         |
| Cortex Block Packages                             | {{< commonSection "/headless/components/purpose/cortex-block-packages.md" >}}        | Required                    | Web Application Server, Application Server |
| Cortex Gateway Databases                          | {{< commonSection "/headless/components/purpose/cortex-gateway-databases.md" >}}     | Required<br />(End of life) | Web Application Server                     |
| [SQL Server Express][] or [SQL Server Standard][] | {{< commonSection "/headless/components/purpose/ms-sql-server.md" >}}                | Required<br />(End of life) | Web Application Server                     |
| [Microsoft Service Fabric][]                      | {{< commonSection "/headless/components/purpose/ms-service-fabric.md" >}}            | Required                    | Application Server                         |
| [Microsoft Service Fabric Explorer][]             | {{< commonSection "/headless/components/purpose/ms-service-fabric-explorer.md" >}}   | Required                    | Application Server                         |
| [Particular NServiceBus][]                        | {{< commonSection "/headless/components/purpose/particular-nservicebus.md" >}}       | Required                    | Application Server                         |
| [Pivotal RabbitMQ][]                              | {{< commonSection "/headless/components/purpose/pivotal-rabbitmq.md" >}}             | Required                    | Application Server                         |
| [Erlang OTP][]                                    | {{< commonSection "/headless/components/purpose/erlang-otp.md" >}}                   | Required                    | Application Server                         |

[Gateway Guide]: {{< url "Cortex.Guides.Gateway.MainDoc" >}}
[Studio Guide]: {{< url "Cortex.Guides.Studio.MainDoc" >}}
[SQL Server Express]: {{< url "MSDownload.SqlServerExpress.2016" >}}
[SQL Server Standard]: {{< url "MSEval.SQLServer.2019" >}}
[Microsoft Service Fabric]: {{< url "MSDocs.ServiceFabric.MainDoc" >}}
[Microsoft Service Fabric Explorer]: {{< url "MSDocs.ServiceFabric.Explorer" >}}
[Particular NServiceBus]: {{< url "Particular.NServiceBus.MainDoc" >}}
[Pivotal RabbitMQ]: {{< url "RabbitMQ.MainDoc" >}}
[Erlang OTP]: {{< url "ErlangOTP.MainDoc" >}}