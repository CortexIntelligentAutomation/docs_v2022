---
title: "Send Email Using SMTP Server"
linkTitle: "Send Email Using SMTP Server"
description: "Sends an email using the specified SMTP server."
---

{{< figure src="/blocks/email-send-email-using-smtp-server-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Email.SendEmail.SendEmailUsingSmtpServerBlock)</p>

## Description

Connects to an [SMTP][] server using the specified [Basic Email Session Details][Basic Email Session Details Property], and sends an [Email Message][Email Message Property].

[Close Session][Close Session Property] can be specified to choose whether the connection to the [SMTP][] server is closed or is kept open for use on subsequent Send Email Using SMTP Server blocks.

## Examples

### Sending an email to a single recipient

This example will send an email from `sender@gmail.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br>`new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority.|
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email to multiple recipients

This example will send an email from `sender@gmail.com` to `recipient1@outlook.com`, `recipient2@outlook.com` and `recipient3@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient1@outlook.com"},  {"Name":  null,  "Address":  "recipient2@outlook.com"}, {"Name": null, "Address": "recipient3@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient1@outlook.com"), new EmailAddress("recipient2@outlook.com"), new EmailAddress("recipient3@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient1@outlook.com`, `recipient2@outlook.com` and `recipient3@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with a CC or BCC recipient

This example will send an email from `sender@gmail.com` to `recipient@outlook.com` with `cc@outlook.com` and `bcc@outlook.com` as the CC and BCC recipients for the email respectively, using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [{"Name": null, "Address": "cc@outlook.com"}], "Bcc": [{"Name": null, "Address": "bcc@outlook.com"}], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: new List<EmailAddress>(){ new EmailAddress("cc@outlook.com") }, bcc: new List<EmailAddress>(){ new EmailAddress("bcc@outlook.com") }, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, both `cc@outlook.com` and `bcc@outlook.com` will also recieve copies of the email as they are listed as CC and BCC recipients, and then the session is closed.

***

### Sending an email with multiple CC or BCC recipients

This example will send an email from `sender@gmail.com` to `recipient@outlook.com` with `cc1@outlook.com` and `cc2@outlook.com` as the CC recipients and `bcc1@outlook.com` and `bcc2@outlook.com` as the BCC recipients for the email, using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [{"Name": null, "Address": "cc1@outlook.com"}, {"Name": null, "Address": "cc2@outlook.com"}], "Bcc": [{"Name": null, "Address": "bcc1@outlook.com"}, {"Name": null, "Address": "bcc2@outlook.com"}], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: new List<EmailAddress>(){ new EmailAddress("cc1@outlook.com"), new EmailAddress("cc2@outlook.com") }, bcc: new List<EmailAddress>(){ new EmailAddress("bcc1@outlook.com"), new EmailAddress("bcc2@outlook.com") }, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, both `cc1@outlook.com` and `cc2@outlook.com` will also recieve copies of the email as they are listed as CC recipients, and both `bcc1@outlook.com` and `bcc2@outlook.com` will recieve copies of the email as they are listed as BCC recipients, and then the session is closed.

***

### Sending an email with a different priority

This example will send an email with [Urgent][] priority from `sender@gmail.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

For more information on what other priority emails can be sent, see [EmailMessagePriority][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": "EmailMessagePriority.Urgent", "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: EmailMessagePriority.Urgent, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [BodyFormat][] is `null`, the email will be sent with a text body.|
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email with [Urgent][] priority is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with an HTML body

This example will send an email with an [HTML][] body from `sender@gmail.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

For more information on what other email body types can be used, see [EmailMessageBodyFormat][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": "EmailMessageBodyFormat.Html", "Body": "<h1>Example email body</h1>", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: EmailMessageBodyFormat.Html, body: "<h1>Example email body</h1>", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br> As [Priority][] is `null`, the email will be sent with [Normal][] priority. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and an [HTML][] body of `"<h1>Example email body<h1/>"`, and then the session is closed.

***

### Sending an email with a single attachment

This example will send an email with a single attachment, `attachment.txt` at the path `C:\attachment.txt` on the server executing the flow, from `sender@gmail.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: new List<string>(){ "C:/attachment.txt" })` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority.<br><br>The attachments are added to the email by providing paths pointing to the attachments to be attached to the email. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email containing a text file attachment, `attachment.txt`, is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email with multiple attachments

This example will send an email with mutiple attachments, `attachment1.txt` and `attachment2.txt` at the paths `C:\attachment1.txt` and `C:\attachment2.txt` respectively on the server executing the flow, from `sender@gmail.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp.gmail.com` on [Port][] `465` with [UseSsl][] set to `true`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@gmail.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": ["C:/attachment1.txt", "C:/attachment2.txt"]}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br> `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@gmail.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: new List<string>(){ "C:/attachment1.txt", "C:/attachment2.txt" })` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority.<br><br>The attachments are added to the email by providing paths pointing to the attachments to be attached to the email. |
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp.gmail.com", "Port": 465, "UseSsl": true}, "Credentials": {"Domain": null, "Username": "sender@gmail.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp.gmail.com", 465, true), credentials: new UserCredentials("sender@gmail.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email containing two text file attachments, `attachment1.txt` and `attachment2.txt`, is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

### Sending an email through a mail server with UseSsl set to false

This example will send an email from `sender@outlook.com` to `recipient@outlook.com` using the [SMTP][] server hosted at `smtp-mail.outlook.com` on [Port][] `587` with [UseSsl][] set to `false`. For more information on whether [UseSsl][] should be set to `true` or `false`, see [Should UseSsl be set to true or false?][]
#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Email Message][Email Message Property] | `($)EmailMessage` with value `{"To":  [{"Name":  null,  "Address":  "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`<br><br>In this example `($)EmailMessage` has been set up using the following [Expression][]:<br><br>`new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@outlook.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `($)EmailMessage` is a variable of type [EmailMessage][]<br><br>As [Priority][] and [BodyFormat][] are `null`, the email will be sent with a text body and [Normal][] priority.|
| [Basic Email Session Details][Basic Email Session Details Property] | `($)BasicEmailSessionDetails` with value `{"ServerDetails": {"Host": "smtp-mail.outlook.com", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "sender@outlook.com", "Password": "encryptedPassword"}}`<br><br>In this example `($)BasicEmailSessionDetails` has been set up using the following [Expression][]:<br><br> `new BasicEmailSessionDetails(serverDetails: new ServerDetails("smtp-mail.outlook.com", 587, false), credentials: new UserCredentials("sender@outlook.com", "encryptedPassword"))` | `($)BasicEmailSessionDetails` is a variable of type [BasicEmailSessionDetails][]<br><br>The [Password][] property in the [UserCredentials][] must be encrypted, for more information on how to encrypt the password, see [EncryptedText][]. |
| [Close Session][Close Session Property] | `($)CloseSession` with value `true` |`($)CloseSession` is a variable of type [Boolean][] |

#### Result

An email is sent from `sender@gmail.com` to `recipient@outlook.com` with a subject of `"Example email subject"` and a text body of `"Example email body"`, and then the session is closed.

***

## Properties

### Email Message

The [Email Message][Email Message Property] to send via the [SMTP][] server specified in the [Basic Email Session Details][Basic Email Session Details Property]. This property contains all of the information in relation to the email to be sent, these are:

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

**TODO: WE ARE HERE IN DOC REVIEW, WE ALSO NEED TO LOOK AT EXAMPLES**

### Basic Email Session Details

The [Basic Email Session Details][Basic Email Session Details Property] object that includes all of the information required to open and maintain a session with an [SMTP][] server, including:

- Server Details - must be provided in order to connect to an [SMTP][] server. This object contains the properties [Host][], [Port][] and [UseSsl][]. For more information on the configuration of this object for this block, see [Should UseSsl be set to true or false?][]
- [Credentials][] - must be provided in order to connect to an [SMTP][] server. This object contains the properties [Username][] and [Password][] to be used for authentication, see [Credentials][] for more information on the configuration of this object for this block.

Note that this property is an [InputOutput][] property and so it must be set to a variable. If the [Close Session][Close Session Property] property is set to `false`, then the session will be kept open and can be used in subsequent Send Email Using SMTP Server blocks which improves performance, see [Opening Sessions][] for more information.

For more detailed information on each of the properties, see [BasicEmailSessionDetails][].

|||
|----------|----------|
| Data Type | [BasicEmailSessionDetails][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)BasicEmailSessionDetails` with no value |

### Close Session

[Close Session][Close Session Property] can be specified to choose whether the session is closed or is kept open for use on subsequent Send Email Using SMTP Server blocks, this defaults to `false` if left blank, please see [Closing Sessions][Closing Sessions] for more information.

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
| [ArgumentException][]                |Thrown when an invalid value is provided for the [BodyFormat][] in the [Email Message][Email Message Property].|
| |Thrown when an invalid value is provided for the [Priority][] in the [Email Message][Email Message Property].|
| [EmailSessionException][]            |Thrown when an invalid [Port][] is provided in the [ServerDetails][] within the [Basic Email Session Details][Basic Email Session Details Property]. For more information, see [Invalid Port][].|
| |Thrown when an invalid [Host][] is provided in the [ServerDetails][] within the [Basic Email Session Details][Basic Email Session Details Property]. For more information, see [Invalid Host][].|
| |Thrown when a connection cannot be established - this is typically because of a mismatch in the [ServerDetails][] object within [Basic Email Session Details][Basic Email Session Details Property] when [UseSsl][] is set to `false` with a [Port][] which requires it to be set to `true`. For more information, see [Should UseSsl be set to true or false?][] |
| |Thrown when a connection cannot be established - this is typically because of a mismatch in the [ServerDetails][] object within [Basic Email Session Details][Basic Email Session Details Property] when [UseSsl][] is set to `true` with a [Port][] which requires it to be set to `false`. For more information, see [Should UseSsl be set to true or false?][] |
| |Thrown when the TLS/SSL certificate is expired on the [Host][] or is untrusted or invalid. For more information, see [SSL Not Supported][].<br><br>Note that this exception has the same category and error code as the above row, this is a known limitation, see [EmailSessionErrorCode Limitations][]. |
| |Thrown when a locally installed anti-virus software replaces the TLS/SSL certificate in order to scan web traffic. For more information, see [SSL Not Supported][].<br><br>Note that this exception has the same category and error code as the above row, this is a known limitation, see [EmailSessionErrorCode Limitations][]. |
| |Thrown when the CRL (Certificate Revocation List) server for the TLS/SSL certificate is down. For more information, see [SSL Not Supported][].<br><br>Note that this exception has the same category and error code as the above row, this is a known limitation, see [EmailSessionErrorCode Limitations][]. |
| |Thrown when the [Username][] and [Password][] in the [Credentials][] within [Basic Email Session Details][Basic Email Session Details Property] is incorrect. For more information, see [Invalid Username and Password][] |
| [FileNotFoundException][]            |Thrown when a non-existent file path is provided in [Attachments][] within [Email Message][Email Message Property]. |
| [IOException][]                      |Thrown when the desired socket is held by another process - re-running the flow typically solves this. |
| [PropertyNullException][]            |Thrown when the [Basic Email Session Details][Basic Email Session Details Property] is `null`. |
| |Thrown when the [Credentials][] within [Basic Email Session Details][Basic Email Session Details Property] is `null`. |
| |Thrown when the [ServerDetails][] within [Basic Email Session Details][Basic Email Session Details Property] is `null`. |
| |Thrown when the [Host][] in [ServerDetails][] within [Basic Email Session Details][Basic Email Session Details Property] is `null`. |
| |Thrown when the [Email Message][Email Message Property] is `null`. |
| |Thrown when the [To][] within [Email Message][Email Message Property] is `null`. |
| |Thrown when the [From][] within [Email Message][Email Message Property] is `null`. |
| |Thrown when the [Address][] in an [EmailAddress][] within [Email Message][Email Message Property] is `null`. |
| [PropertyEmptyException][]           |Thrown when the [Host][] in [ServerDetails][] within [Basic Email Session Details][Basic Email Session Details Property] is empty. |
| |Thrown when the [To][] within [Email Message][Email Message Property] is empty. |
| |Thrown when the [Address][] in an [EmailAddress][] within [Email Message][Email Message Property] is empty. |
| [PropertyValueOutOfRangeException][] |Thrown when the [Port][] in the [ServerDetails][] within [Basic Email Session Details][Basic Email Session Details Property] is below 1 or above 65535. |
| [SmtpCommandException][]             |Thrown when the [Address][] in an [EmailAddress][] within [Email Message][Email Message Property] is not of the correct format.|
| [UnauthorizedAccessException][]      |Thrown when access is denied to a file provided in [Attachments][] within [Email Message][Email Message Property].|

For more information on the [EmailSessionException][] including error codes, see [EmailSessionException][].

## Remarks

### Should UseSsl be set to true or false?

A [ServerDetails][] must be provided in the [Basic Email Session Details][Basic Email Session Details Property] in order to connect to an [SMTP][] server. The value of the [UseSsl][] property inside this object depends on the [Host][] and [Port][] being connected to. There are two types of [SSL][]/[TLS][] connections that can occur:

- [SSL][]/[TLS][] is used as soon as a connection is established
- [SSL][]/[TLS][] is used via the STARTTLS command if it is available

The above two points correspond to the [UseSsl][] property being set to `true` and `false` respectively. As such, generally the following rules can be followed to determine whether [UseSsl][] should be set to `true` or `false`:

- If the [Port][] being connected to is `465` then [UseSsl][] should be set to `true`
- If the [Port][] being connected to is `25` or `567` then [UseSsl][] should be set to `false`

For more information, see [ServerDetails][].

### Credentials

A [UserCredentials][] must be provided in the [Basic Email Session Details][Basic Email Session Details Property] in order to connect to an SMTP server. The value of the [Username][] property may be encrypted if a user wishes, however the [Password][] must be encrypted otherwise an exception will be thrown when the object is created. For more information on how to encrypt the password, see [EncryptedText][].

Note that the [UserCredentials][] object also contains a [Domain][] property which does not need to be specified for use in this block.

For more information, see [UserCredentials][].

### Opening Sessions

The Send Email Using SMTP Server block automatically handles creating and opening sessions for the specified [Basic Email Session Details][Basic Email Session Details Property] using the following rules:

- If a session does not exist, a new session will be created, opened and used when the block runs.
- If a session already exists but is closed, the session will be opened and used when the block runs.
- If a session already exists and is open, the session will be used when the block runs.

[Basic Email Session Details][Basic Email Session Details Property] is an [InputOutput][] and so it must be set to a [Variable][], because of this it can be used to keep the session alive across multiple Send Email Using SMTP Server blocks as long as [Close Session][Close Session Property] is set to `false`. Keeping the session open helps increase the performance of the block due to the subsequent blocks not having to spend resources creating and opening sessions for each execution.

Note that for all [SSL][] connections, the protocol to be used will be negotiated with the server depending on which protocols are available. Similarly, the [SASL][] mechanism to be used will be negotiated with the mail server based on the available mechanisms.

For information on how to explicitly close a connection, please see [Closing Sessions][].

### Closing Sessions

Sessions can be explicitly closed by setting [Close Session][Close Session Property] to `true`. This causes the session to be closed after the [Email Message][Email Message Property] has been sent.

If [Close Session][Close Session Property] is set to `false` the connection will be closed when the [Variable][] that [Basic Email Session Details][Basic Email Session Details Property] is set to goes out of scope or the flow ends, whichever happens first. For more information about variables and scope, please see [Variables][].

For information on how to open a connection, please see [Opening Sessions][].

### Known Limitations

- This block cannot currently send emails if the [Credentials][] are `null`.
- This block cannot currently send emails if the [Password][] in the [Credentials][] is empty or `null`.

These limitations may be removed in the future.

[Email Message Property]: {{< ref "#email-message" >}}
[Basic Email Session Details Property]: {{< ref "#basic-email-session-details" >}}
[Close Session Property]: {{< ref "#close-session" >}}

[Should UseSsl be set to true or false?]: {{< ref "#should-usessl-be-set-to-true-or-false" >}}
[Credentials]: {{< ref "#credentials" >}}
[Opening Sessions]: {{< ref "#opening-sessions" >}}
[Closing Sessions]: {{< ref "#closing-sessions" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[EmailSessionException]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.MainDoc" >}}
[Invalid Port]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.InvalidPort" >}}
[Invalid Host]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.InvalidHost" >}}
[SSL Not Supported]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.SslUnsupported" >}}
[Invalid Username and Password]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.InvalidUserCredentials" >}}
[creating an EmailMessage using a constructor]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.CreateAnEmailMessage" >}}

[EmailSessionErrorCode Limitations]: {{< url "Cortex.Reference.DataTypes.Email.EmailSessionErrorCode.Limitations" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}
[FileNotFoundException]: {{< url "MSDocs.DotNet.Api.System.IO.FileNotFoundException" >}}
[IOException]: {{< url "MSDocs.DotNet.Api.System.IO.IOException" >}}
[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}
[PropertyValueOutOfRangeException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyValueOutOfRangeException.MainDoc" >}}
[SmtpCommandException]: {{< url "MimeKit.Docs.SmtpCommandException" >}}
[UnauthorizedAccessException]: {{< url "MSDocs.DotNet.Api.System.UnauthorizedAccessException" >}}

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

[EmailAddress]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.MainDoc" >}}
[Address]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.Address" >}}

[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[Normal]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Normal" >}}
[Urgent]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.Urgent" >}}

[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}
[HTML]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.HTML" >}}

[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[Domain]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Domain" >}}
[Username]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Username" >}}
[Password]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Password" >}}

[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
[Host]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Host" >}}
[Port]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.Port" >}}
[UseSsl]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.UseSsl" >}}

[Boolean]: {{< url "Cortex.Reference.DataTypes.ConditionalLogic.Boolean.MainDoc" >}}
[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[Variables]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}

[SASL]: {{< url "Cortex.Reference.Glossary.P-T.SASL" >}}
[SMTP]: {{< url "Cortex.Reference.Glossary.P-T.SMTP" >}}
[SSL]: {{< url "Cortex.Reference.Glossary.P-T.SSL" >}}
[TLS]: {{< url "Cortex.Reference.Glossary.P-T.TLS" >}}
