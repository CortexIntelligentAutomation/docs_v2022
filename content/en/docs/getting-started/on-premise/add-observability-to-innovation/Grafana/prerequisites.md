---
title: "Prerequisites"
linkTitle: "Prerequisites"
description: "Information about the prerequisites required on each server type for installation."
weight: 20
---
# {{< param title >}}

The prerequisites required for each server role (as described in [Architecture][]) are laid out in this guide. These must be considered before undertaking the installation.

## Hardware Requirements

| Server&nbsp;Role | Servers&nbsp;Required | CPU&nbsp;Cores&nbsp;(>&nbsp;2GHz) | RAM&nbsp;(GB) | Disk&nbsp;(GB) |  
|------------------|-----------------------|-----------------------------------|---------------|----------------------|
| Web&nbsp;Application&nbsp;Server | 1 | 4+&nbsp;*Recommended*<br>2&nbsp;*Minimum* | 16+&nbsp;*Recommended*<br>8&nbsp;*Minimum* | 50+&nbsp;(SSD)&nbsp;*Recommended*<br>40&nbsp;(HDD)&nbsp;*Minimum*<br>5+&nbsp;free&nbsp;on&nbsp;installation&nbsp;drive |

{{% alert title="Note" %}}
The application servers (as described in {{< ahref "Cortex.GettingStarted.OnPremise.InstallInnovationOnly.MultipleServerWithHA.Architecture" "Architecture" >}}) to which Promtail will be added have already been installed as part of the Innovation install process and do not require any hardware modifications for the observability platform installation.
{{% /alert %}}

## Software Requirements

| Server&nbsp;Role | Windows&nbsp;Server[^1] | IIS[^2] | Other&nbsp;Software |
|------------------|-------------------------|---------|----------|
| Web Application Server[^3] | [2019 (x64)][] *Recommended*<br>[2016 (x64)][] | 10.0.17763[^4]<br>10.0.14393[^5]<br>IIS Basic Authentication[^6]<br>[URL Rewrite module 2.1][] | [Grafana 8.5.4][] (Enterprise Edition)<br>[Grafana Loki 2.5.0][] (loki-windows-amd64.exe.zip)|
| Application Server | [2019 (x64)][] *Recommended*<br>[2016 (x64)][] | | [Promtail 2.5.0][] (promtail-windows-amd64.exe.zip) |

[^1]: Windows Server Standard and Datacenter editions are supported. Filesystem **must be NTFS** and networking **must use IPv4**. Linux is not supported, but may be in the future.
[^2]: IIS is supported; other web servers, including IIS Express are not supported.
[^3]: This should be a separate machine from the one used for Innovation Web Application Server.
[^4]: Ships as a windows role within Windows Server 2019.
[^5]: Ships as a windows role within Windows Server 2016.
[^6]: Installed during the [Install IIS Basic Authentication][] configuration steps.

## Domain Requirements

All servers must be on the same domain and cannot be domain controllers.

## Web Browser Requirements

Grafana supports the latest versions of the following browsers:

* Chrome/Chromium
* Firefox
* Safari
* Microsoft Edge

{{% alert title="Note" %}}
Always enable JavaScript in your browser. Running Grafana without JavaScript enabled in the browser is not supported.
{{% / alert %}}

## Additional Application Server Requirements

### Security Requirements

#### Installation User

A domain user which is a member of the Local Administrators group on all Application Servers must be available to perform the installation.

## Additional Web Application Server Requirements

### Security Requirements

#### Installation User

A domain user which is a member of the Local Administrators group on the Web Application Server must be available to perform the installation.

#### Port Requirements

The observability platform requires a range of [firewall ports to be opened][Port Requirements] on the Web Application Server.

#### Certificate Requirements

{{% alert title="Note" %}}
For production systems, it is recommended that X.509 SSL wildcard certificates are obtained from a Certificate Authority and used for installation. For non-production systems, self-signed certificates may be used.
{{% / alert %}}

An X.509 SSL wildcard certificate should be used to:

* Secure communication between Promtail on the Application Servers and the reverse proxy configured for Grafana Loki on the Web Application Server.
* Secure communication between Grafana end users and the Grafana Web Application on the Web Application Server.

The certificate can be obtained from a Certificate Authority, such as [Let’s Encrypt][], and must meet the following requirements:

* Subject field must be in a wildcard format, pertaining to the domain of the Application Servers (e.g. `CN=*.domain.com`).
* Subject alternative names must include any additional host names that should be able to be used to access the Grafana Web Application.
* Certificate file must be in a .PFX with a known password.
* Certificate file must also be available in a .PEM file format.
* Certificate file must contain the full chain of certificates.
* Certificate file must include the private key.

The files should be placed in a known location on the Web Application Server. This location will be required when [configuring Grafana to use HTTPS][].

IIS requires an X.509 SSL certificate to be installed on the Web Application Server. The certificate must have the following property configured:

* Subject Alternative Names (SAN): At minimum, the FQDN of the Server. It can also include NetBIOS Name, IP address, localhost, 127.0.0.1

If the user tries navigating to an address not in the SAN list, they will receive a certificate error.

Wildcard certificates and self-signed certificates can also be used. However, self-signed certificates are not recommended for production instances. Details on how to create a self-signed certificate can be found at [Create Self-Signed Certificates][].

More information about importing the certificate is given during installation.

#### TLS Requirements

A set of non-compulsory security measures is recommended to be applied to Web Application Servers to prevent attacks that exploit known industry security vulnerabilities. This includes disabling all versions of SSL and TLS apart from TLS 1.2. And disabling all cipher suites apart from the following:

* TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
* TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256

See [SSL Best Practices][] for a full list of the security changes which will be applied. The `Cortex.Innovation.Install.SSLBestPractises.ps1` script is provided during installation to apply these security changes to the Web Application Server.

## Next Steps?

1. [Install Grafana][]

[2016 (x64)]: {{< url "Microsoft.Downloads.Windows.Server2016" >}}
[2019 (x64)]: {{< url "Microsoft.Downloads.Windows.Server2019" >}}
[Architecture]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Architecture" >}}
[Create Self-Signed Certificates]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Advanced.CreateSelfSignedCertificates" >}}
[Grafana 8.5.4]: {{< url "Grafana.SelfManaged.Downloads.GrafanaWebApp.Windows" >}}
[Grafana Loki 2.5.0]: {{< url "Grafana.SelfManaged.Downloads.GrafanaLoki.MainDoc" >}}
[Install Grafana]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallGrafana.MainDoc" >}}
[Install IIS Basic Authentication]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallLoki.InstallIISBasicAuthentication" >}}]
[Let’s Encrypt]: {{< url "LetsEncrypt.MainDoc" >}}
[Promtail 2.5.0]:  {{< url "Grafana.SelfManaged.Downloads.GrafanaLoki.MainDoc" >}}
[SSL Best Practices]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Advanced.SSLBestPractices" >}}
[URL Rewrite module 2.1]: {{< url "IIS.Downloads.UrlRewrite-2_1" >}}
[Port Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.Advanced.PortRequirements" >}}
[configuring Grafana to use HTTPS]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallGrafana.ConfigureHTTPS" >}}