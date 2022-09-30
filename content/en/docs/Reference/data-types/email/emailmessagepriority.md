---
title: "EmailMessagePriority"
linkTitle: "EmailMessagePriority"
description: "Defines the priority of an email."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.EmailMessagePriority)</p>

## Summary

The `EmailMessagePriority` data type is used to define the priority an email.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `EmailMessagePriority`                                 |
| **Full Name:**         | `Cortex.DataTypes.Email.EmailMessagePriority`          |
| **Alias:**             | N/A                                                    |
| **Description:**       | Defines the priority of an email.                      |
| **Default Value:**     | `EmailMessagePriority.Normal`                          |
| **Can be used as:**    | `EmailMessagePriority`, `Object`, `dynamic`            |
| **Can be cast to:**    | N/A                                                    |

## Values

### Normal

| | |
|-|-|
| **Name:**    | Normal                                                |
| **Value:**   | [Int32][] with value `0`                              |
| **Notes:**   | Used when an email is marked with normal urgency.     |

### NonUrgent

| | |
|-|-|
| **Name:**    | NonUrgent                                             |
| **Value:**   | [Int32][] with value `1`                              |
| **Notes:**   | Used when an email is marked with non-urgent urgency. |

### Urgent

| | |
|-|-|
| **Name:**    | Urgent                                                |
| **Value:**   | [Int32][] with value `2`                              |
| **Notes:**   | Used when an email is marked with urgent urgency.     |

## Remarks

### Create an EmailMessagePriority

The following table shows some of the ways that `EmailMessagePriority` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use an enum expression | `EmailMessagePriority.Normal` | `EmailMessagePriority.Normal`| Expression |  |
| Use an enum expression | `EmailMessagePriority.NonUrgent` | `EmailMessagePriority.NonUrgent`| Expression |  |
| Use an enum expression | `EmailMessagePriority.Urgent` | `EmailMessagePriority.Urgent`| Expression |  |

An `EmailMessagePriority` can also be created using the Literal Editor by selecting the desired option from the dropdown list containing the range of options.

### Casting an Int32 to EmailMessagePriority

| Example | Result | Editor&nbsp;Support |
|-|-|-|
| `(EmailMessagePriority)($)IntVar` where `($)IntVar` has a value `0` | `EmailMessagePriority.Normal` | Expression |
| `(EmailMessagePriority)($)IntVar` where `($)IntVar` has a value `1` | `EmailMessagePriority.NonUrgent` | Expression |
| `(EmailMessagePriority)($)IntVar` where `($)IntVar` has a value `2` | `EmailMessagePriority.Urgent` | Expression |

### Convert EmailMessagePriority to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)EmailMessagePriority.ToString()` where `($)EmailMessagePriority` has a value of `EmailMessagePriority.Normal`| `"Normal"` | Expression | ToString will return the Name of the enum value |
| Use `Convert Object To Text` block | where `Object` property has a value of `EmailMessagePriority.Normal` | `"Normal"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `EmailMessagePriority.Normal` | `"0"` | N/A  | See [Convert Object To Json][] |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailMessagePriority`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailMessagePriority`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailMessagePriority`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [EmailMessage][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}

[EmailMessage]: {{< url "Cortex.Reference.DataTypes.Email.EmailMessage.MainDoc" >}}
[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
