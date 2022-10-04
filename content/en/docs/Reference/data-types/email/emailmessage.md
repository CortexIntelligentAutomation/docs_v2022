---
title: "EmailMessage"
linkTitle: "EmailMessage"
description: "Defines an email. "
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.EmailMessage)</p>

## Summary

The `EmailMessage` data type is used to define an email.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `EmailMessage`                                         |
| **Full Name:**         | `Cortex.DataTypes.Email.EmailMessage`                  |
| **Alias:**             | N/A                                                    |
| **Description:**       | Defines an email.                                      |
| **Default Value:**     | `null`                                                 |
| **Can be used as:**    | `EmailMessage`, `Object`, `dynamic`                    |
| **Can be cast to:**    | N/A                                                    |

## Properties

### To

The To property is used to define the recipients of the email. It is a [IList][]&lt;[EmailAddress][]&gt;, where each [EmailAddress][] item is a recipient.

| | |
|--------------------|---------------------------|
| Data Type | [IList][]&lt;[EmailAddress][]&gt; |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [IList][]&lt;[EmailAddress][]&gt; with value `new List<EmailAddress>(){ new EmailAddress("") }` |

### From

The From property is used to define who/where the email is from.

| | |
|--------------------|---------------------------|
| Data Type | [EmailAddress][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [EmailAddress][] with value:<br>Name: `""` <br> Address: `""` |

### Cc

The Cc property is used to define the Cc addresses for the email. It is a [IList][]&lt;[EmailAddress][]&gt;, where each [EmailAddress][] item is a Cc address of the email.

| | |
|--------------------|---------------------------|
| Data Type | [IList][]&lt;[EmailAddress][]&gt; |
| Is Advanced | `true` |
| Default Editor | [Expression][] |
| Default Value | [IList][]&lt;[EmailAddress][]&gt; with value `null` |

### Bcc

The Bcc property is used to define the Bcc addresses for the email. It is a [IList][]&lt;[EmailAddress][]&gt;, where each [EmailAddress][] item is a Bcc address of the email.

| | |
|--------------------|---------------------------|
| Data Type | [IList][]&lt;[EmailAddress][]&gt; |
| Is Advanced | `true` |
| Default Editor | [Expression][] |
| Default Value | [IList][]&lt;[EmailAddress][]&gt; with value `null` |

### Priority

The Priority property is used to define the priority of the email, for more information on the range of values this can take, see [EmailMessagePriority][].

| | |
|--------------------|---------------------------|
| Data Type | [EmailMessagePriority][] |
| Is Advanced | `true` |
| Default Editor | [Literal][] |
| Default Value | [EmailMessagePriority][] with value `Normal` |

### Subject

The Subject property is used to define the subject of the email.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [String][] with value `""` |

### Body Format

The Body Format property is used to define the format of the email body, for more information on the range of values this can take, see [EmailMessageBodyFormat][].

| | |
|--------------------|---------------------------|
| Data Type | [EmailMessageBodyFormat][] |
| Is Advanced | `true` |
| Default Editor | [Literal][] |
| Default Value | [EmailMessageBodyFormat][] with value `Text` |

### Body

The Body property is used to define the body of the email.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [String][] with value `$@""` |

### Attachments

The Attachments property is used to define any attachments to be sent with the email. It is an [IList][]&lt;[String][]&gt; where each item in the list is a path pointing to the attachment.

| | |
|--------------------|---------------------------|
| Data Type | [IList][]&lt;[String][]&gt; |
| Is Advanced | `true` |
| Default Editor | [Expression][] |
| Default Value | [IList][]&lt;[String][]&gt; with value `null` |

## Remarks

### Create an EmailMessage

The following table shows some of the ways that `EmailMessage` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `EmailMessage` constructor | `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@outlook.com"), cc: null, bcc: null, priority: null, subject: "Example email subject", bodyFormat: null, body: "Example email body", attachments: null)` | `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`| Expression | N/A |
| | `new EmailMessage(to: new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, from: new EmailAddress("sender@outlook.com"), cc: new List<EmailAddress>(){ new EmailAddress("cc@outlook.com") }, bcc: new List<EmailAddress>(){ new EmailAddress("bcc@outlook.com") }, priority: EmailMessagePriority.Urgent, subject: "Example email subject", bodyFormat: EmailMessageBodyFormat.Text, body: "Example email body", attachments: new List<string>(){ "C:/attachment.txt" })` | `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [{"To": [{"Name": null, "Address": "cc@outlook.com"}], "Bcc": [{"To": [{"Name": null, "Address": "bcc@outlook.com"}], "Priority": EmailMessagePriority.Urgent, "Subject": "Example email subject", "BodyFormat": EmailMessageBodyFormat.Text, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}`| Expression | N/A |

A `EmailMessage` can also be created using the Literal Editor by filling in the necessary values for the following properties:

| Property      | Data Type                | Example                                               | Notes                                         |
|-|-|-|-|
| `To`          | `IList<EmailAddress>`    | `new List<EmailAddress>(){ "recipient@outlook.com" }` | The recipients of the email. |
| `From`        | `EmailAddress`           | Name: `Sender`<br>Address: `sender@outlook.com` | The sender of the email. |
| `Cc`          | `IList<EmailAddress>`    | `new List<EmailAddress>(){ "cc@outlook.com" }` | The [Cc][Cc Property] addresses. |
| `Bcc`         | `IList<EmailAddress>`    | `new List<EmailAddress>(){ "bcc@outlook.com" }` | The [Bcc][Bcc Property] addresses. |
| `Priority`    | `EmailMessagePriority`   | `Normal` | The [Priority][Priority Property] of the email. |
| `Subject`     | `String`                 | `"Example subject"` | The [Subject][Subject Property] of the email. |
| `BodyFormat`  | `EmailMessageBodyFormat` | `Text` | The [Body Format][Body Format Property] of the email body. |
| `Body`        | `String`                 | `"Example body"` | The email [Body][Body Property]. |
| `Attachments` |  `IList<String>`         | `new List<string>(){ "C:/attachment.txt" }` | A list of file paths pointing to [Attachments][Attachments Property]. |

### Convert EmailMessage to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)EmailMessage.ToString()` | `"Cortex.DataTypes.Email.EmailMessage"` | Expression | ToString will return the Full Name of the EmailMessage Data Type |
| Use `Convert Object To Text` block | where `Object` property has a value of `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [{"To": [{"Name": null, "Address": "cc@outlook.com"}], "Bcc": [{"To": [{"Name": null, "Address": "bcc@outlook.com"}], "Priority": EmailMessagePriority.Urgent, "Subject": "Example email subject", "BodyFormat": EmailMessageBodyFormat.Text, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}` | `"Cortex.DataTypes.Email.EmailMessage"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [{"To": [{"Name": null, "Address": "cc@outlook.com"}], "Bcc": [{"To": [{"Name": null, "Address": "bcc@outlook.com"}], "Priority": EmailMessagePriority.Urgent, "Subject": "Example email subject", "BodyFormat": EmailMessageBodyFormat.Text, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}` | `"{\r\n  \"To\": [\r\n    {\r\n      \"Name\": null,\r\n      \"Address\": \"recipient@outlook.com\"\r\n    }\r\n  ],\r\n  \"From\": {\r\n    \"Name\": null,\r\n    \"Address\": \"sender@outlook.com\"\r\n  },\r\n  \"Cc\": [\r\n    {\r\n      \"Name\": null,\r\n      \"Address\": \"cc@outlook.com\"\r\n    }\r\n  ],\r\n  \"Bcc\": [\r\n    {\r\n      \"Name\": null,\r\n      \"Address\": \"bcc@outlook.com\"\r\n    }\r\n  ],\r\n  \"Priority\": 2,\r\n  \"Subject\": \"Example email subject\",\r\n  \"BodyFormat\": 0,\r\n  \"Body\": \"Example email body\",\r\n  \"Attachments\": [\r\n    \"C:/attachment.txt\"\r\n  ]\r\n}"` | N/A  | See [Convert Object To Json][] |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailMessage`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailMessage`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailMessage`.
  
### Known Limitations

Currently, if the `ToString()` method is used on a EmailMessage, then its Full Name will be returned; instead of a representation of the data within the EmailMessage.

In future this limitation may be removed.

## See Also

### Related Data Types

* [EmailAddress][]
* [EmailMessagePriority][]
* [EmailMessageBodyFormat][]

[Cc Property]: {{< ref "#cc" >}}
[Bcc Property]: {{< ref "#bcc" >}}
[Priority Property]: {{< ref "#priority" >}}
[Subject Property]: {{< ref "#subject" >}}
[Body Format Property]: {{< ref "#body-format" >}}
[Body Property]: {{< ref "#body" >}}
[Attachments Property]: {{< ref "#attachments" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[EmailAddress]: {{< url "Cortex.Reference.DataTypes.Email.EmailAddress.MainDoc" >}}
[EmailMessagePriority]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessagePriority.MainDoc" >}}
[EmailMessageBodyFormat]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessageBodyFormat.MainDoc" >}}

[IList]: {{< url "Cortex.Reference.DataTypes.Collections.IList.MainDoc" >}}
[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
