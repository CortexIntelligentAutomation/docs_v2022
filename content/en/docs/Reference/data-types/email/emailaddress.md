---
title: "EmailAddress"
linkTitle: "EmailAddress"
description: "Defines an email address."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.EmailAddress)</p>

## Summary

The `EmailAddress` data type is used to define an email address.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `EmailAddress`                                         |
| **Full Name:**         | `Cortex.DataTypes.Email.EmailAddress`                  |
| **Alias:**             | N/A                                                    |
| **Description:**       | Defines an email address.                              |
| **Default Value:**     | `null`                                                 |
| **Can be used as:**    | `EmailAddress`, `Object`, `dynamic`                    |
| **Can be cast to:**    | N/A                                                    |

## Properties

### Name

The Name property is used to define the name associated with an email address.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Is Advanced | `true` |
| Default Editor | [Literal][] |
| Default Value | [String][] with value `""` |

### Address

The Address property is used to define the actual email address.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [String][] with value `""` |

## Remarks

### Create an EmailMessage

The following table shows some of the ways that `EmailMessage` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `EmailAddress` constructor | `new EmailAddress(address: "sender@outlook.com")`| `{"Name": null, "Address": "sender@outlook.com"}` | Expression |  |
| Use a `EmailAddress` constructor | `new EmailAddress(name: "Sender", address: "sender@outlook.com")`| `{"Name": "Sender", "Address": "sender@outlook.com"}` | Expression |  |

A `EmailAddress` can also be created using the Literal Editor by filling in the necessary values for the following properties:

| Property | Data Type | Example | Notes |
|-|-|-|-|
| `Name` | `String`    | `"Sender"`             | The [Name][Name Property] associated with the email address. |
| `Address` | `String`    | `"sender@outlook.com"` | The email address. |

### Convert EmailAddress to Text

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailAddress`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailAddress`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailAddress`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [EmailMessage][]

[Name Property]: {{< ref "#name" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
