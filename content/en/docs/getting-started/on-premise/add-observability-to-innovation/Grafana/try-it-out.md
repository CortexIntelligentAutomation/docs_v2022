---
title: "Try it Out"
linkTitle: "Try it Out"
description: "Information about trying out Grafana Observability Dashboards for the first time."
weight: 60
---

# {{< param title >}}

## Check Dashboards are Displaying Data
{{% alert title="Note" %}}
This test uses the test flow published as part of testing the {{< ahref "Cortex.GettingStarted.OnPremise.InstallInnovationOnly.MultipleServerWithHA.TryItOutPublishedFlow" "Innovation installation" >}}. An alternative flow can be used that exists on the system and is able to be executed. If using an alternative flow, substitute the flow name and package name as appropriate.
{{% / alert %}}

1. Open an HTTP client, such as [Postman][]. Make a request with the following format:
    | Property      | Value                                                                               |
    |---------------|-------------------------------------------------------------------------------------|
    | Action        | POST                                                                                |
    | URL           | https://{FQDN of Load Balancer Server}/api/default/default/flows/{Flow Name}/executions?packageName={Package Name}<br />e.g. https://load-balancer&#46;domain&#46;com/api/default/default/flows/NewFlow/executions?packageName=NewPackage|
    | Content Type  | application/json                                                                    |
    | Body          | {}                                                                                  |
    | Authentication| Basic                                                                               |
    | Username      | The value used for `ApiGatewayBasicAuthUserName` when installing Application Services              |
    | Password      | The value used for `ApiGatewayBasicAuthPwd` when installing Application Services (Unencrypted) |

    {{% alert title="Note" %}} If you used self-signed certificates when installing the Application Servers you will need to disable SSL certificate validation in your HTTP client. {{% /alert %}}

1. Once the request has completed, using a web browser, log in to your configured Grafana.
1. Click the Dashboards icon ![Dashboards Icon](/images/DashboardsIcon.png 'Dashboards Icon') in the side menu, and then click *Browse*.
1. Click the folder name that the dashboards were imported to.
1. Click the *Flow Execution Requests* dashboard to open it.
1. The request made at step 1 should be visible on the dashboard.
{{% alert title="Note" %}}
If other requests have been made then there may be more than one request visible on the dashboard.
{{% / alert %}}
1. Click the Dashboards icon ![Dashboards Icon](/images/DashboardsIcon.png 'Dashboards Icon') in the side menu, and then click *Browse*.
1. Click the folder name that the dashboards were imported to.
1. Click the *Platform Health* dashboard to open it.
1. The request made at step 1 should be visible on the dashboard.
{{% alert title="Note" %}}
If other requests have been made then there may be more than one request visible on the dashboard.
{{% / alert %}}

[Postman]: {{< url "Postman.Downloads.MainDoc" >}}
