---
title: "EmailMessageBodyFormat"
linkTitle: "EmailMessageBodyFormat"
description: "Defines the format of an email body."
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
| **Description:**       | Defines the format of an email body.                   |
| **Default Value:**     | `0`                                                    |
| **Can be used as:**    | `EmailMessageBodyFormat`, `Object`, `dynamic`          |
| **Can be cast to:**    | N/A                                                    |

## Values

### Text

| | |
|-|-|
| **Name:**    | Text                                          |
| **Value:**   | [Int32][] with value `0`                      |
| **Notes:**   | Used when an email body format is plain text. |

### Html

| | |
|-|-|
| **Name:**    | Html                                          |
| **Value:**   | [Int32][] with value `1`                      |
| **Notes:**   | Used when an email body format is HTML.       |

## Remarks

### Create an EmailMessageBodyFormat

The following table shows some of the ways that `EmailMessageBodyFormat` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use an enum expression | `EmailMessageBodyFormat.Text` | `EmailMessageBodyFormat.Text`| Expression | N/A |
| Use an enum expression | `EmailMessageBodyFormat.Html` | `EmailMessageBodyFormat.Html`| Expression | N/A |

An `EmailMessageBodyFormat` can also be created using the Literal Editor by selecting the desired option from the dropdown list containing the range of options.

### Convert EmailMessageBodyFormat to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)EmailMessageBodyFormat.ToString()` where `($)EmailMessageBodyFormat` has a value of `EmailMessageBodyFormat.Text`| `"Text"` | Expression | ToString will return the Name of the enum value |
| Use `Convert Object To Text` block | where `Object` property has a value of `EmailMessageBodyFormat.Text` | `"Text"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `EmailMessageBodyFormat.Text` | `"0"` | N/A  | See [Convert Object To Json][] |

### Casting an Int32 to EmailMessageBodyFormat

[Int32][] values can be cast to an `EmailMessageBodyFormat` in the following ways:

| Example | Result | Editor&nbsp;Support |
|-|-|-|
| `(EmailMessageBodyFormat)($)IntVar` where `($)IntVar` has a value `0` | `EmailMessageBodyFormat.Text` | Expression |
| `(EmailMessageBodyFormat)($)IntVar` where `($)IntVar` has a value `1` | `EmailMessageBodyFormat.Html` | Expression |

For more information on casting [Int32][] values to enums, see [Working with Enums][].

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailMessageBodyFormat`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailMessageBodyFormat`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailMessageBodyFormat`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [EmailMessage][]
  
### Related Concepts

* [Working with Enums][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}

[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}
[Working with Enums]: {{< url "Cortex.Reference.Concepts.WorkingWith.Enums.MainDoc" >}}
[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
