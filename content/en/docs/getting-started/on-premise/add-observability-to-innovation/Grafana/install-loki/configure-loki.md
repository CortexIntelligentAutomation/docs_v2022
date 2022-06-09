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
1. Run the downloaded installer.
1. When promted by the Web Platform Installer, click *Install*.
1. On the *Prerequisites* page click *I Accept* to agree to the license terms for the module.
1. Once the install has completed, click *Finish*.
1. Click *Exit* to close the Web Platform Installer.

### Set Up Reverse Proxy

To set up a reverse proxy carry out the following configuration.

#### Add a New Website

1. Run IIS Manager.
1. In the *Connection* pane expand the server.
1. Right-clik on *Sites* and select *Add Website...* from the menu.
1. In the *Add Website* window:
    - Provide the site name, e.g. `Grafana Loki`.
    - Set the *Physical path* to location where the site will be stored and ensure that the path exists, e.g. `C:\inetpub\wwwroot\Grafana Loki`.
    - For *Binding* set:
        - *Type*: `https`
        - *IP address*: `All unasigned`
        - *Port*: `2100`
    - *Host name*: The fully qualified machine name of the Web Application Server. This must match what has been set for the SSL certificates.
    - *SSL certificate*: Select the certificate created as part of the [Certificate Requirements][] instructions.
    - Click *OK* to add the website.

#### Enable Basic Authentication

1. In the *Connection* pane browse to *Sites*.
1. Select the newly created website.
1. Double-click on the *Authentication* icon.
1. Disable *Anonymous Authentication*.
1. Enable *Basic Authentication*.

#### Restart the Website

1. In the *Connection* pane browse to *Sites*.
1. Select the newly created website.
1. In the *Manage Website* pane click "Restart"

#### Create Loki User

1. Run Windows PowerShell as Administrator.
1. Execute the following command to create a new user in the system:

    ```Powershell
    New-LocalUser "Login" -Password (ConvertTo-SecureString "Password" -AsPlainText -force) -FullName "Name" -Description "Description" –PasswordNeverExpires
    ```

    Where:
    - *Login*: The username of the user to be added to the system.
    - *Password*: The password for the user account.
    - *Name*: The full nema for the user account.
    - *Description*: The description of the user account.

## Next Steps?

1. [Install Promtail][]

[Certificate Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.CertificateRequirements" >}}
[Install Promtail]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.InstallPromtail.MainDoc" >}}
[Software Requirements]: {{< url "Cortex.GettingStarted.OnPremise.AddObservabilityToInnovation.Grafana.SoftwareRequirements" >}}
