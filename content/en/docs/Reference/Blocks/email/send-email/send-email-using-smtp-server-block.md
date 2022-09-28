---
title: "Send Email Using SMTP Server"
linkTitle: "Send Email Using SMTP Server"
description: "Sends an email using the specified SMTP server."
---

{{< figure src="/blocks/email-send-email-using-smtp-server-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Email.SendEmail.SendEmailUsingSmtpServerBlock)</p>

## Description

Connects to an SMTP server using the specified [Basic Email Session Details][Basic Email Session Details Property], and sends an [Email Message][Email Message Property].

[Close Session][Close Session Property] can be specified to choose whether the connection to the SMTP server is closed or is kept open for use on subsequent Send Email Using SMTP Server blocks.

## Examples

### Sending an email to a single recipient

This example will send an email from `sender@outlook.com` to `recipient@outlook.com` using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [],"Priority": null, "Subject": "Example email subject", "BodyFormat":null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, null, "Example email subject", null, "Example email body", null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority and BodyFormat are null, the email will be sent with a text body and normal priority. For more information, see [EmailMessage][].|
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email to multiple recipients

This example will send an email from `sender@gmail.com` to `recipient1@outlook.com`, `recipient2@outlook.com` and `recipient3@outlook.com` using the SMTP server hosted at `smtp.gmail.com` on port `465` with useSsl set to `true`.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To":  [{"Name":  null,  "Address":  "recipient1@outlook.com"},  {"Name":  null,  "Address":  "recipient2@outlook.com"}, {"Name": null, "Address": "recipient3@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient1@outlook.com"), new EmailAddress("recipient2@outlook.com"), new EmailAddress("recipient3@outlook.com") }, new EmailAddress("sender@gmail.com"), null, null, null, "Example email subject", null, "Example email body", null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority and BodyFormat are null, the email will be sent with a text body and normal priority. For more information, see [EmailMessage][]. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp.gmail.com", 465, true), new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient1@outlook.com`, `recipient2@outlook.com` and `recipient3@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with CC or BCC addresses

This example will send an email from `sender@outlook.com` to `recipient@outlook.com` with `cc1@outlook.com` and `cc2@outlook.com` as the CCs for the email, using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

Note that the same approach would be used in order to send an email with BCC addresses.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [{"Name": null, "Address": "cc1@outlook.com"}, {"Name": null, "Address": "cc2@outlook.com"}], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), new List<EmailAddress>(){ new EmailAddress("cc1@outlook.com"), new EmailAddress("cc2@outlook.com") }, null, null, "Example email subject", null, "Example email body", null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority and BodyFormat are null, the email will be sent with a text body and normal priority. For more information, see [EmailMessage][]. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, both `cc1@outlook.com` and `cc2@outlook.com` will also recieve copies of the email as they are CC'd, and then the session is closed.

***

### Sending an email with a different priority

This example will send an email with Urgent priority from `sender@outlook.com` to `recipient@outlook.com` using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

For more information on what other priority emails can be sent, see [EmailMessagePriority][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": EmailMessagePriority.Urgent, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, EmailMessagePriority.Urgent, "Example email subject", null, "Example email body", null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As BodyFormat is null, the email will be sent with a text body. For more information, see [EmailMessage][].|
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email with Urgent priority is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with a HTML body

This example will send an email with a HTML body from `sender@outlook.com` to `recipient@outlook.com` using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

For more information on what other email body types can be used, see [EmailMessageBodyFormat][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": EmailMessageBodyFormat.Html, "Body": "<h1>Example email body</h1>", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, null, "Example email subject", EmailMessageBodyFormat.Html, "<h1>Example email body</h1>", null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority is null, the email will be sent with normal priority. For more information, see [EmailMessage][]. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a HTML body of `"<h1>Example email body<h1/>"`, and then the session is closed.

***

### Sending an email with a single attachment

This example will send an email with a single attachment, `attachment.txt` at `C:\attachment.txt`, from `sender@outlook.com` to `recipient@outlook.com` using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, null, "Example email subject", null, "Example email body", new List<string>(){ "C:/attachment.txt" })` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority and BodyFormat are null, the email will be sent with a text body and normal priority.<br><br>The attachments are added to the email by providing paths pointing to the attachments to be attached to the email. For more information, see [EmailMessage][]. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email containing a text file attachment, `attachment.txt`, is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with mutiple attachments

This example will send an email with mutiple attachments, `attachment1.txt` and `attachment2.txt` at `C:\attachment1.txt` and `C:\attachment2.txt` respectively, from `sender@outlook.com` to `recipient@outlook.com` using the SMTP server hosted at `smtp-mail.outlook.com` on port `587` with useSsl set to `false` (for more information, see [Setting useSsl to false][]).

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage`, with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": ["C:/attachment1.txt", "C:/attachment2.txt"]}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, null, "Example email subject", null, "Example email body", new List<string>(){ "C:/attachment1.txt", "C:/attachment2.txt" })` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As Priority and BodyFormat are null, the email will be sent with a text body and normal priority.<br><br>The attachments are added to the email by providing paths pointing to the attachments to be attached to the email. For more information, see [EmailMessage][]. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails`, with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(new ServerDetails("smtp-mail.outlook.com", 587, false), new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The password in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession`, with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email containing two text file attachments, `attachment1.txt` and `attachment2.txt`, is sent from `sender@outlook.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

## Properties

### Email Message

The [Email Message][Email Message Property] to send via the SMTP server specified in the [Basic Email Session Details][Basic Email Session Details Property]. This property contains all of the information in relation to the email to be sent, these are:

- To
- From
- CC
- BCC
- Priority
- Subject
- BodyFormat
- Body
- Attachments

For more detailed information on each of the properties within the [Email Message][Email Message Property], see [EmailMessage][].

|||
|----------|----------|
| Data Type | [EmailMessage][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | [EmailMessage][] with value `{}` |

### Basic Email Session Details

The [Basic Email Session Details][Basic Email Session Details Property] object that includes all of the information required to connect to an SMTP server, including:

- Server Details - must be provided in order to connect to an SMTP server. This contains the see host, port and whether or not to use SSL, see [ServerDetails][] for more information.
- Credentials - must be provided in order to connect to an SMTP server and is used for SMTP Authentication. This object contains host, username and password. The username and password must provided to send an email, see [UserCredentials][] for more information.

For more information, see [BasicEmailSessionDetails][].

|||
|----------|----------|
| Data Type | [BasicEmailSessionDetails][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | [BasicEmailSessionDetails][] with value `{}` |

### Close Session

[Close Session][Close Session Property] can be specified to choose whether the connection to the SMTP server is closed or is kept open for use on subsequent Send Email Using SMTP Server blocks, this defaults to `false` if left blank, please see [Closing Sessions][Closing Sessions] for more information.

|||
|-----------------|----------|
| Data Type       | [Boolean][] |
| Property Type   | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor  | [Literal][] |
| Default Value   | [Boolean][] with value `true` |

## Exceptions

The exceptions thrown by the block can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| [ArgumentException][]                |Thrown when an invalid value is provided for the bodyFormat in the [Email Message][Email Message Property].|
||Thrown when an invalid value is provided for the priority in the [Email Message][Email Message Property].|
| [EmailSessionException][]            |Thrown when an invalid port is provided in the serverDetails within the [Basic Email Session Details][Basic Email Session Details Property].|
||Thrown when an invalid host is provided in the serverDetails within the [Basic Email Session Details][Basic Email Session Details Property].|
||Thrown when a connection cannot be established - this is typically because of a mismatch in the serverDetails object within [Basic Email Session Details][Basic Email Session Details Property] when useSsl is set to `false` with a port which requires SSL.|
||Thrown when a connection cannot be established - this is typically because of a mismatch in the serverDetails object within [Basic Email Session Details][Basic Email Session Details Property] when useSsl is set to `true` with a port which does not support SSL.|
||Thrown when the TLS/SSL certificate is expired on the host or is untrusted.|
||Thrown when a locally installed anti-virus software replaces the TLS/SSL certificate in order to scan web traffic.|
||Thrown when the CRL (Certificate Revocation List) server for the TLS/SSL certificate is down.|
||Thrown when the host has an invalid SSL certificate.|
||Thrown when the username and/or password in the userCredentials within [Basic Email Session Details][Basic Email Session Details Property] is incorrect.|
| [FileNotFoundException][]            |Thrown when a non-existent file path is provided in attachments within [Email Message][Email Message Property].|
| [IOException][]                      |Thrown when the desired socket is held by another process - re-running the flow typically solves this.|
| [PropertyNullException][]            |Thrown when the [Basic Email Session Details][Basic Email Session Details Property] is null.|
||Thrown when the credentials within [Basic Email Session Details][Basic Email Session Details Property] is null.|
||Thrown when the serverDetails within [Basic Email Session Details][Basic Email Session Details Property] is null.|
||Thrown when the host in serverDetails within [Basic Email Session Details][Basic Email Session Details Property] is null.|
||Thrown when the [Email Message][Email Message Property] is null.|
||Thrown when the to within [Email Message][Email Message Property] is null.|
||Thrown when the from within [Email Message][Email Message Property] is null.|
||Thrown when the address in an emailAddress within [Email Message][Email Message Property] is null.|
| [PropertyEmptyException][]           |Thrown when the host in serverDetails within [Basic Email Session Details][Basic Email Session Details Property] is empty.|
||Thrown when the to within [Email Message][Email Message Property] is empty.|
||Thrown when the address in an emailAddress in within [Email Message][Email Message Property] is empty.|
| [PropertyValueOutOfRangeException][] |Thrown when the port in the serverDetails within [Basic Email Session Details][Basic Email Session Details Property] is below 1 or above 65535|
| [SmtpCommandException][]             |Thrown when the address in an emailAddress within [Email Message][Email Message Property] is not of the correct format (RFC-5321).|
| [UnauthorizedAccessException][]      |Thrown when access is denied to a file provided in attachments within [Email Message][Email Message Property].|

For more information on the [EmailSessionException][] including error codes, see [EmailSessionException][].

## Remarks

### Opening Sessions

The Send Email Using SMTP Server block automatically handles creating and opening sessions for the specified [Basic Email Session Details][Basic Email Session Details Property] using the following rules:

- If a session does not exist, a new session will be created, opened and used when the block runs.
- If a session already exists but is closed, the session will be opened and used when the block runs.
- If a session already exists and is open, the session will be used when the block runs.

[Basic Email Session Details][Basic Email Session Details Property] is an [InputOutput][] and so it must be set to a [Variable][], because of this it can be used to keep the session alive across multiple Send Email Using SMTP Server blocks as long as [Close Session][Close Session Property] is set to `false`. Keeping the session open helps increase the performance of the block due to the subsequent blocks not having to spend resources creating and opening sessions for each execution.

For information on how to explicitly close a connection, please see [Closing Sessions][].

#### Setting useSsl to `false`

If useSsl is set to `false` in serverDetails within [Basic Email Session Details][Basic Email Session Details Property], the client will not attempt to make an SSL-wrapped connection, however TLS/SSL may still be used if the mail server supports the STARTTLS extension. For all SSL connections, the protocol to be used will be negotiated with the server depending on the which protocols are available. Similarly, the SASL mechanism to be used will be negotiated with the mail server based on the avialable mechanisms.

### Closing Sessions

Sessions can be explicitly closed by setting [Close Session][Close Session Property] to `true`. This causes the session to be closed after the [Email Message][Email Message Property] has been sent.

If [Close Session][Close Session Property] is set to `false` the connection will be closed when the [Variable][] that [Basic Email Session Details][Basic Email Session Details Property] is set to goes out of scope or the flow ends, whichever happens first. For more information about variables and scope, please see [Variables][].

For information on how to open a connection, please see [Opening Sessions][].

### Known Limitations

This block cannot currently send emails if credentials are not provided.

[Email Message Property]: {{< ref "#email-message" >}}
[Basic Email Session Details Property]: {{< ref "#basic-email-session-details" >}}
[Close Session Property]: {{< ref "#close-session" >}}

[Opening Sessions]: {{< ref "#opening-sessions" >}}
[Closing Sessions]: {{< ref "#closing-sessions" >}}
[Setting useSsl to false]: {{< ref "#setting-usessl-to-false" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}
[EmailSessionException]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.MainDoc" >}}
[FileNotFoundException]: {{< url "MSDocs.DotNet.Api.System.IO.FileNotFoundException" >}}
[IOException]: {{< url "MSDocs.DotNet.Api.System.IO.IOException" >}}
[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}
[PropertyValueOutOfRangeException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyValueOutOfRangeException.MainDoc" >}}
[SmtpCommandException]: {{< url "MimeKit.Docs.SmtpCommandException" >}}
[UnauthorizedAccessException]: {{< url "MSDocs.DotNet.Api.System.UnauthorizedAccessException" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}
[EmailAddress]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.MainDoc" >}}
[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}
[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}
[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}

[Boolean]: {{< url "Cortex.Reference.DataTypes.ConditionalLogic.Boolean.MainDoc" >}}
[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
