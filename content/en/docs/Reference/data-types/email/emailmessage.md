---
title: "EmailMessage"
linkTitle: "EmailMessage"
description: "Used to define an email. "
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
| **Description:**       | The data type used to define an email.                 |
| **Default Value:**     | null                                                   |
| **Can be used as:**    | `EmailMessage`, `Object`, `dynamic`                    |
| **Can be cast to:**    | N/A                                                    |

## Properties

### To

The To property is used to define the recipients of the email.

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

The Cc property is used to define the Cc addresses for the email.

| | |
|--------------------|---------------------------|
| Data Type | [IList][]&lt;[EmailAddress][]&gt; |
| Is Advanced | `true` |
| Default Editor | [Expression][] |
| Default Value | [IList][]&lt;[EmailAddress][]&gt; with value `null` |

### Bcc

The Bcc property is used to define the Bcc addresses for the email.

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
| Use a `EmailMessage` constructor | `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), null, null, null, "Example email subject", null, "Example email body", null)` | `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [], "Bcc": [], "Priority": null, "Subject": "Example email subject", "BodyFormat": null, "Body": "Example email body", "Attachments": []}`| Expression |  |
| | `new EmailMessage(new List<EmailAddress>(){ new EmailAddress("recipient@outlook.com") }, new EmailAddress("sender@outlook.com"), new List<EmailAddress>(){ new EmailAddress("cc@outlook.com") }, new List<EmailAddress>(){ new EmailAddress("bcc@outlook.com") }, EmailMessagePriority.Urgent, "Example email subject", EmailMessageBodyFormat.Text, "Example email body", new List<string>(){ "C:/attachment.txt" })` | `{"To": [{"Name": null, "Address": "recipient@outlook.com"}], "From": {"Name": null, "Address": "sender@outlook.com"}, "Cc": [{"To": [{"Name": null, "Address": "cc@outlook.com"}], "Bcc": [{"To": [{"Name": null, "Address": "bcc@outlook.com"}], "Priority": EmailMessagePriority.Urgent, "Subject": "Example email subject", "BodyFormat": EmailMessageBodyFormat.Text, "Body": "Example email body", "Attachments": ["C:/attachment.txt"]}`| Expression |  |

A `EmailMessage` can also be created using the Literal Editor by filling in the necessary values for the following properties:

...

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailMessage`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailMessage`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailMessage`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [EmailAddress][]
* [EmailMessagePriority][]
* [EmailMessageBodyFormat][]

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