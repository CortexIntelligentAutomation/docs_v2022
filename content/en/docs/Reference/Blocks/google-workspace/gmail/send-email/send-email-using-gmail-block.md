---
title: "Send Email Using Gmail"
linkTitle: "Send Email Using Gmail"
description: "Sends an email using the SMTP server hosted by Gmail."
---

{{< figure src="/blocks/google-workspace-send-email-using-gmail-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.GoogleWorkspace.Gmail.SendEmail.SendEmailUsingGmailBlock)</p>

## Description

Connects to the [SMTP][] server hosted by [Gmail][] using the specified [Gmail Session Details][Gmail Session Details Property], and sends an [Email Message][Email Message Property].

[Close Session][Close Session Property] can be specified to choose whether the connection to the [SMTP][] server hosted by [Gmail][] is closed or is kept open for use on subsequent Send Email Using Gmail blocks.

## Examples

## Properties

### Email Message

The [Email Message][Email Message Property] to send via the [SMTP][] server hosted by [Gmail][] specified in the [Gmail Session Details][Gmail Session Details Property]. This property contains all of the information in relation to the email to be sent, these are:

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

### Gmail Session Details

### Close Session

[Close Session][Close Session Property] can be specified to choose whether the session is closed or is kept open for use on subsequent Send Email Using Gmail blocks, this defaults to `false` if left blank, please see [Closing Sessions][Closing Sessions] for more information.

|||
|-----------------|----------|
| Data Type       | [Boolean][] |
| Property Type   | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor  | [Literal][] |
| Default Value   | [Boolean][] with value `true` |

## Exceptions

## Remarks

### Setting UseSsl

The [ServerDetails][] within the [Gmail Session Details][Gmail Session Details Property] specifies which [SMTP][] server to connect to. The value of the [UseSsl][] property inside this object depends on the [Host][] and [Port][] being connected to. There are two types of [SSL][]/[TLS][] connections that can occur:

- [SSL][]/[TLS][] is used as soon as a connection is established
- [SSL][]/[TLS][] is used via the STARTTLS command if it is available

The above two points correspond to the [UseSsl][] property being set to `true` and `false` respectively. As such, generally the following rules can be followed to determine whether [UseSsl][] should be set to `true` or `false`:

- If the [Port][] being connected to is `465` then [UseSsl][] should be set to `true`
- If the [Port][] being connected to is `25` or `587` then [UseSsl][] should be set to `false`

### Setting Credentials

### Opening Sessions

### Closing Sessions

Sessions can be explicitly closed by setting [Close Session][Close Session Property] to `true`. This causes the session to be closed after the [Email Message][Email Message Property] has been sent.

If [Close Session][Close Session Property] is set to `false` the session will be closed when the [Variable][] that [Gmail Session Details][Gmail Session Details Property] is set to goes out of scope or the flow ends, whichever happens first. For more information about variables and scope, please see [Variables][].

For information on how to open a session, please see [Opening Sessions][].

### Known Limitations

None

[Email Message Property]: {{< ref "#email-message" >}}
[Gmail Session Details Property]: {{< ref "#gmail-session-details" >}}
[Close Session Property]: {{< ref "#close-session" >}}
[Opening Sessions]: {{< ref "#opening-sessions" >}}
[Closing Sessions]: {{< ref "#closing-sessions" >}}

[Boolean]: {{< url "Cortex.Reference.DataTypes.ConditionalLogic.Boolean.MainDoc" >}}
[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

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

[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
[Host]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Host" >}}
[Port]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Port" >}}
[UseSsl]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.UseSsl" >}}

[EmailAddress]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.MainDoc" >}}
[Address]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.Address" >}}

[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[Normal]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Normal" >}}
[Urgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Urgent" >}}
[NonUrgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.NonUrgent" >}}

[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}
[HTML]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.HTML" >}}
[Text]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.Text" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}

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
