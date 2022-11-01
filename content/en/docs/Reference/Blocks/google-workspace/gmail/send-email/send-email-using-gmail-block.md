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

Sending emails using a username and password is not recommended and is being phased out by [Gmail][]. Using a username and password will currently only work for [Gmail][] accounts associated with a Google Workspace that has access enabled for less secure apps. Instead, it is recommended to use an app password or OAuth, for more information, see [Less Secure Apps][].

In the following examples, where a [UserCredentials][] is used in the [Gmail Session Details][Gmail Session Details Property], the [Password][] property can be either the password associated with the username (if the account is associated with a Google Workspace with access enabled for less secure apps) or an app password.

For more information, see [Setting Credentials][].

### Sending an email using OAuth

***

### Sending an email using a username and app password

***

### Sending an email using a username and password

This example will send an email from `sender@gmail.com` to `recipient@outlook.com`. The example uses the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` which requires [UseSsl][] to be to set to `true` within the [Gmail Session Details][Gmail Session Details Property].

For more information about when [UseSsl][] should be set to `true` or `false`, see [Setting UseSsl][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br>`new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a [Text][] body and [Normal][] priority.|
| [Gmail Session Details][Gmail Session Details Property] | `($)GmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)GmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new GmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)GmailSessionDetails` is a variable of type [GmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email with [Normal][] priority is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a [Text][] body of `"Example email body"`, and then the session is closed.

***

### Sending an email to a single recipient

***

### Sending an email to multiple recipients

***

### Sending an email with a CC or BCC recipient

***

### Sending an email with multiple CC or BCC recipients

***

### Sending an email with a different priority

***

### Sending an email with an HTML body

***

### Sending an email with a single attachment

***

### Sending an email with multiple attachments

***

### Sending an email with UseSsl set to false

***

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

### How does Priority affect sending an email?

### How does BodyFormat affect sending an email?

### Attachments

Attachments can be sent in an email by providing a list of file paths in the [Attachments][] property of the [Email Message][Email Message Property]. For more information concerning attaching files to an email, see the sections below.

#### Supported file path formats

Each file path in the [Attachments][] within the [Email Message][Email Message Property] can be an:

- Absolute file path
- Relative file path
- UNC file path

where each file path must be accessible from the server executing the flow.

For more information about each of these supported file path formats, please see [File & Folder Paths][].

#### File paths need escaping

Each file path in the [Attachments][] within the [Email Message][Email Message Property] requires \ characters to be escaped, otherwise each unescaped \ will be reported as an Invalid property value message when trying to debug the flow.

Escaping can be done in two ways:

- Escaping the `\` character with another `\` character (e.g. `"C:\\Attachments\\attachment.txt"`), or
- Prepending an `@` character before the start of the File Path (e.g. `@"C:\Attachments\attachment.txt"`)

#### Null file path

If `null` is provided as a file path in the [Attachments][] within the [Email Message][Email Message Property], an [ArgumentNullException][] is thrown.

#### Empty file path

If an empty string is provided as a file path in the the [Attachments][] within the [Email Message][Email Message Property], an [ArgumentException][] is thrown.

#### File path does not exist

If a file path in the [Attachments][] within the [Email Message][Email Message Property] does not exist, a [FileNotFoundException][] is thrown.

#### Invalid file path

If a file path in the [Attachments][] within the [Email Message][Email Message Property] is invalid (i.e. contains any of the following characters: ", *, ?, |, <, >, :, \, /), an [IOException][] will be thrown.

#### File path points to a folder

If a file path in the [Attachments][] within the [Email Message][Email Message Property] points to a folder, an [UnauthorizedAccessException][] will be thrown.

#### File path contains leading spaces

If a file path in the [Attachments][] within the [Email Message][Email Message Property] contains leading spaces they are not removed and an [IOException][] will be thrown; however, trailing spaces are removed.

#### File path contains only whitespace or the NUL character

If a file path in the [Attachments][] within the [Email Message][Email Message Property] contains only whitespace (i.e. `"  "`) or the NUL character (i.e. `\0`), an [ArgumentException][] will be thrown.

#### File path exceeds the system-defined maximum length

If a file path in the [Attachments][] within the [Email Message][Email Message Property] exceeds the system-defined maximum length (typically 32,767), a [PathTooLongException][] will be thrown.

#### User does not have necessary permissions to attach the file

If the user the flow is executing as does not have permissions to access the file at the provided file path in the [Attachments][] within the [Email Message][Email Message Property], an [UnauthorizedAccessException][] will be thrown.

#### Attachment size limit

The combined size of all the [Attachments][] within the [Email Message][Email Message Property] must be less than the limit specified by the email service provider. If the combined size of all of the attachments is greater than the limit, an [SmtpCommandException][] will be thrown.

For [Outlook][] this is `20 MB` and for [Gmail][] this is `25 MB`, for more information on the size limits for other email service providers, see the help provided by the respective email service provider.

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
[Setting Credentials]: {{< ref "#setting-credentials" >}}
[Setting UseSsl]: {{< ref "#setting-usessl" >}}
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

[GmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.GoogleWorkspace.Gmail.GmailSessionDetails.MainDoc" >}}

[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
[Host]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Host" >}}
[Port]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Port" >}}
[UseSsl]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.UseSsl" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[Domain]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Domain" >}}
[Username]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Username" >}}
[Password]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Password" >}}

[EmailAddress]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.MainDoc" >}}
[Address]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.Address" >}}

[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[Normal]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Normal" >}}
[Urgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Urgent" >}}
[NonUrgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.NonUrgent" >}}

[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}
[HTML]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.HTML" >}}
[Text]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.Text" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}
[ArgumentNullException]: {{< url "MSDocs.DotNet.Api.System.ArgumentNullException" >}}
[FileNotFoundException]: {{< url "MSDocs.DotNet.Api.System.IO.FileNotFoundException" >}}
[IOException]: {{< url "MSDocs.DotNet.Api.System.IO.IOException" >}}
[PathTooLongException]: {{< url "MSDocs.DotNet.Api.System.IO.PathTooLongException" >}}
[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}
[PropertyValueOutOfRangeException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyValueOutOfRangeException.MainDoc" >}}
[Property Is Invalid]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyValueOutOfRangeException.PropertyIsInvalid">}}
[SmtpCommandException]: {{< url "MimeKit.Docs.SmtpCommandException" >}}
[UnauthorizedAccessException]: {{< url "MSDocs.DotNet.Api.System.UnauthorizedAccessException" >}}
[UnencryptedTextException]: {{< url "Cortex.Reference.Exceptions.Common.UnencryptedTextException.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[File & Folder Paths]: {{< url "Cortex.Reference.Concepts.WorkingWith.FilesAndFolders.Paths.MainDoc" >}}

[SASL]: {{< url "Cortex.Reference.Glossary.P-T.SASL" >}}
[SMTP]: {{< url "Cortex.Reference.Glossary.P-T.SMTP" >}}
[SSL]: {{< url "Cortex.Reference.Glossary.P-T.SSL" >}}
[TLS]: {{< url "Cortex.Reference.Glossary.P-T.TLS" >}}
[BCC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.BCC" >}}
[CC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.CC" >}}
[CRL]: {{< url "Cortex.Reference.Glossary.A-E.CRL" >}}
[Gmail]: {{< url "Cortex.Reference.Glossary.F-J.Gmail" >}}
[Outlook]: {{< url "Cortex.Reference.Glossary.K-O.Outlook" >}}

[Less Secure Apps]: {{< url "Google.Authentication.LessSecureApps.MainDoc" >}}
[RFC 5321]: {{< url "IETF.Email.RFC5321" >}}
