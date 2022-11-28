---
title: "Send Email Using Microsoft 365"
linkTitle: "Send Email Using Microsoft 365"
description: "Sends an email using the SMTP server hosted by Outlook."
---

{{< figure src="/blocks/microsoft365-send-email-using-microsoft365-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Microsoft365.Outlook.SendEmail.SendEmailUsingMicrosoft365Block)</p>

{{% alert type="warning" title="Warning" %}}This page is not complete and currently only contains basic information. This will be completed in the future.{{% /alert %}}

## Description

Connects to the [SMTP][] server hosted by [Outlook][] using the specified [Credentials][Credentials Property], and sends an [Email Message][Email Message Property].

This block only supports authentication via OAuth (using [Microsoft365OAuthCredentials][] or [Microsoft365OAuthCertificateCredentials][]), to send an email using basic authentication, see [Send Email Using SMTP Server][].

## Examples

### Sending an email using client credentials

This example will send an email from `sender@outlook.com` to `recipient@outlook.com` using the [SMTP][] server hosted by [Outlook][].

The OAuth mechanism in this example uses client credentials. Therefore, for this example to work correctly, the [Credentials][Credentials Property] provided must be a [Microsoft365OAuthCredentials][].

For more information on:

- What each of the properties inside [Microsoft365OAuthCredentials][] needs to be, see [Microsoft365OAuthCredentials][]
- How to set up an [Outlook][] account so that this authentication mechanism can be used, see [Setting up an Outlook account for OAuth authentication using client credentials][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br>`new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@outlook.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a [Text][] body and [Normal][] priority.|
| [Credentials][Credentials Property] | `($)Credentials` with value `{"ClientId": "clientId", "ClientSecret": "encryptedClientSecret", "TenantId": "tenantId", ObjectId: "objectId"}`<br><br>In this example `($)Credentials` has been set up using the following [Expression][]:<br><br> `new Microsoft365OAuthCredentials(clientId: "clientId", clientSecret: "encryptedClientSecret", tenantId: "tenantId", objectId: "objectId")` | `($)Credentials` is a variable of type [Microsoft365OAuthCredentials][]<br><br>The [ClientSecret][] property in the [Microsoft365OAuthCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |

#### Result

An email with [Normal][] priority is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a [Text][] body of `"Example email body"`, and then the session is closed.

***

### Sending an email using certificate credentials

This example will send an email from `sender@outlook.com` to `recipient@outlook.com` using the [SMTP][] server hosted by [Outlook][].

The OAuth mechanism in this example uses certificate credentials. Therefore, for this example to work correctly:

- [Credentials][Credentials Property] provided must be a [Microsoft365OAuthCertificateCredentials][]
- [CertificatePath][] must be a path pointing to a certificate accessible from the server executing the flow

For more information on:

- What each of the properties inside [Microsoft365OAuthCertificateCredentials][] needs to be, see [Microsoft365OAuthCertificateCredentials][]
- How to set up an [Outlook][] account so that this authentication mechanism can be used, see [Setting up an Outlook account for OAuth authentication using certificate credentials][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br>`new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@outlook.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a [Text][] body and [Normal][] priority.|
| [Credentials][Credentials Property] | `($)Credentials` with value `{"CertificatePath": "C:\\certificate.pfx", "CertificatePassword": "encryptedPassword", "ClientId": "clientId", "TenantId": "tenantId", "ObjectId": "objectId"}`<br><br>In this example `($)Credentials` has been set up using the following [Expression][]:<br><br> `new Microsoft365OAuthCertificateCredentials(certificatePath: @"C:\certificate.pfx", certificatePassword: "encryptedPassword", clientId: "clientId", tenantId: "tenantId", objectId: "objectId")` | `($)Credentials` is a variable of type [Microsoft365OAuthCertificateCredentials][]<br><br>The [CertificatePassword][] property in the [Microsoft365OAuthCertificateCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |

#### Result

An email with [Normal][] priority is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a [Text][] body of `"Example email body"`, and then the session is closed.

***

## Properties

### Email Message

The [Email Message][Email Message Property] to send via the [SMTP][] server hosted by [Outlook][]. This property contains all of the information in relation to the email to be sent, these are:

- [To][]
- [From][]
- [Cc][]
- [Bcc][]
- [Priority][]
- [Subject][]
- [BodyFormat][]
- [Body][]
- [Attachments][]

Note that if the properties [Priority][] and [BodyFormat][] are set to `null` when [creating an EmailMessage using a constructor][], the email will be sent with [Normal][] priority and with a [Text][] body.

For more detailed information on each of the properties, see [EmailMessage][].

|||
|----------|----------|
| Data Type | [EmailMessage][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | [EmailMessage][] with value shown below: |

```json
{
  "To": [
    {
      "Name": null,
      "Address": ""
    }
  ],
  "From": {
    "Name": "",
    "Address": ""
  },
  "Cc": [],
  "Bcc": [],
  "Priority": "EmailMessagePriority.Normal",
  "Subject": "",
  "BodyFormat": "EmailMessageBodyFormat.Text",
  "Body": "",
  "Attachments": []
}
```

### Credentials

The [Credentials][Credentials Property] object that includes all of the information required to connect to an [SMTP][] server hosted by [Outlook][]. There are multiple data types that can be used which depends on the desired OAuth mechanism:

- [Microsoft365OAuthCredentials][]: Using client credentials. For information on:
  - What each of the properties inside [Microsoft365OAuthCredentials][] needs to be, see [Microsoft365OAuthCredentials][]
  - How to set up an [Outlook][] account so that this authentication mechanism can be used, see [Setting up an Outlook account for OAuth authentication using client credentials][]
- [Microsoft365OAuthCertificateCredentials][]: Using certificate credentials. For information on:
  - What each of the properties inside [Microsoft365OAuthCertificateCredentials][], see [Microsoft365OAuthCertificateCredentials][]
  - How to set up an [Outlook][] account so that this authentication mechanism can be used, see [Setting up an Outlook account for OAuth authentication using certificate credentials][]

|||
|----------|----------|
| Data Type | [Microsoft365Credentials][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | [Microsoft365OAuthCredentials][] with value shown below: |

```json
{
  "ClientId": "",
  "ClientSecret": "",
  "TenantId": "",
  "ObjectId": "",
}
```

## Exceptions

## Remarks

### Known Limitations

None

[Email Message Property]: {{< ref "#email-message" >}}
[Credentials Property]: {{< ref "#credentials" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}
[To]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.To" >}}
[From]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.From" >}}
[Cc]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Cc" >}}
[Bcc]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Bcc" >}}
[Priority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Priority" >}}
[Subject]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Subject" >}}
[BodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.BodyFormat" >}}
[Body]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Body" >}}
[Attachments]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.Attachments" >}}
[creating an EmailMessage using a constructor]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.CreateAnEmailMessage" >}}

[Microsoft365Credentials]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365Credentials.MainDoc" >}}

[Microsoft365OAuthCredentials]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365OAuthCredentials.MainDoc" >}}
[ClientSecret]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365OAuthCredentials.ClientSecret" >}}

[Microsoft365OAuthCertificateCredentials]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365OAuthCertificateCredentials.MainDoc" >}}
[CertificatePath]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365OAuthCertificateCredentials.CertificatePath" >}}
[CertificatePassword]: {{< url "Cortex.Reference.DataTypes.Microsoft365.Authentication.OAuth.Microsoft365OAuthCertificateCredentials.CertificatePassword" >}}

[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[Normal]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Normal" >}}
[Urgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Urgent" >}}
[NonUrgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.NonUrgent" >}}

[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}
[HTML]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.HTML" >}}
[Text]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.Text" >}}

[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}

[Send Email Using SMTP Server]: {{< url "Cortex.Reference.Blocks.Email.SendEmail.SendEmailUsingSmtpServer.MainDoc" >}}

[Setting up an Outlook account for OAuth authentication using client credentials]: {{< url "Cortex.Reference.Concepts.WorkingWith.Email.Authentication.SettingUpClientCredentialsOutlook" >}}
[Setting up an Outlook account for OAuth authentication using certificate credentials]: {{< url "Cortex.Reference.Concepts.WorkingWith.Email.Authentication.SettingUpCertificateCredentialsOutlook" >}}

[SASL]: {{< url "Cortex.Reference.Glossary.P-T.SASL" >}}
[SMTP]: {{< url "Cortex.Reference.Glossary.P-T.SMTP" >}}
[SSL]: {{< url "Cortex.Reference.Glossary.P-T.SSL" >}}
[TLS]: {{< url "Cortex.Reference.Glossary.P-T.TLS" >}}
[BCC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.BCC" >}}
[CC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.CC" >}}
[CRL]: {{< url "Cortex.Reference.Glossary.A-E.CRL" >}}
[Gmail]: {{< url "Cortex.Reference.Glossary.F-J.Gmail" >}}
[Outlook]: {{< url "Cortex.Reference.Glossary.K-O.Outlook" >}}
[RFC 5321]: {{< url "IETF.Email.RFC5321" >}}
