---
title: "EmailMessageBodyFormat"
linkTitle: "EmailMessageBodyFormat"
description: "Used to define the format of an email body."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.EmailMessageBodyFormat)</p>

## Summary

The `EmailMessageBodyFormat` data type is used to define the format of an email body.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `EmailMessageBodyFormat`                               |
| **Full Name:**         | `Cortex.DataTypes.Email.EmailMessageBodyFormat`        |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type used to define the format of an email body. |
| **Default Value:**     | `EmailMessageBodyFormat.Text`                          |
| **Can be used as:**    | `EmailMessageBodyFormat`, `Object`, `dynamic`          |
| **Can be cast to:**    | N/A                                                    |

## Values

### Text

The Text value is used when an email body format is plain text.

### Html

The Html value is used when an email body format is HTML.

## Remarks

### Create an EmailMessageBodyFormat

The following table shows some of the ways that `EmailMessageBodyFormat` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use an expression | `EmailMessageBodyFormat.Text` | `EmailMessageBodyFormat.Text`| Expression |  |
| Use an expression | `EmailMessageBodyFormat.Html` | `EmailMessageBodyFormat.Html`| Expression |  |

A `EmailMessageBodyFormat` can also be created using the Literal Editor by filling in the necessary values for the following properties:

...

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailMessageBodyFormat`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailMessageBodyFormat`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailMessageBodyFormat`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [EmailMessage][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}
