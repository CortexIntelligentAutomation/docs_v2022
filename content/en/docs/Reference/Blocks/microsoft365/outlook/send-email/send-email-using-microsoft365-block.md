---
title: "Send Email Using Microsoft365"
linkTitle: "Send Email Using Microsoft365"
description: "Sends an email using Microsoft365."
---

{{< figure src="/blocks/microsoft365-send-email-using-microsoft365-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Microsoft365.Outlook.SendEmail.SendEmailUsingMicrosoft365Block)</p>

{{% alert type="warning" title="Warning" %}}This page is not complete and currently only contains basic information. This will be completed in the future.{{% /alert %}}

## Description

Connects to an [SMTP][] server hosted by [Outlook][] using the specified [Credentials][Credentials Property], and sends an [Email Message][Email Message Property].

This block only supports authentication via OAuth (using [Microsoft365OAuthCredentials][] or [Microsoft365OAuthCertificateCredentials][]), to send an email using basic authentication, see [Send Email Using SMTP Server][].

## Examples

### Sending an email using client credentials

### Sending an email using certificate credentials

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

Note that if the properties [Priority][] and [BodyFormat][] are set to `null` when [creating an EmailMessage using a constructor][], the email will be sent with [Normal][] priority and with a text body.

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

[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[Normal]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Normal" >}}
[Urgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Urgent" >}}
[NonUrgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.NonUrgent" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}

[Send Email Using SMTP Server]: {{< url "Cortex.Reference.Blocks.Email.SendEmail.SendEmailUsingSmtpServer.MainDoc" >}}

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
