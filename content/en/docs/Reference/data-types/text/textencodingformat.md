---
title: "TextEncodingFormat"
linkTitle: "TextEncodingFormat"
description: "The available types of encoding format available for use with text encode and decode blocks."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Text.TextEncodingFormat)</p>

## Summary

The `TextEncodingFormat` data type is used to represent an encoding format that is used in the [Encode Text][] and [Decode Text][] blocks.

`TextEncodingFormat` is an [enum][Working with Enums] data type, which means it has a defined set of values, where each value has an associated [String][] name and [Int32][] value.

| | |
|-|-|
| **Category:**          | Text                                                  |
| **Name:**              | `TextEncodingFormat`                                |
| **Full Name:**         | `Cortex.DataTypes.Text.Encode.TextEncodingFormat`         |
| **Alias:**             | N/A                                                    |
| **Description:**       | The encoding format used while encoding/decoding Text. |
| **Size:**              | `4` bytes                                              |
| **Default Value:**     | `(TextEncodingFormat)0`                             |
| **Can be used as:**    | `TextEncodingFormat`, `Object`, `dynamic`           |
| **Can be cast to:**    | `Int16` (e.g. `(Int16)TextEncodingFormat.Base64` or `(System.Int16)TextEncodingFormat.Base64` or `(short)TextEncodingFormat.Base64`)  |
|                        | `Int32` (e.g. `(Int32)TextEncodingFormat.Base64` or `(System.Int32)TextEncodingFormat.Base64` or `(int)TextEncodingFormat.Base64`)  |
|                        | `Int64` (e.g. `(Int64)TextEncodingFormat.Base64` or `(System.Int64)TextEncodingFormat.Base64` or `(long)TextEncodingFormat.Base64`)  |
|                        | `Single` (e.g. `(Single)TextEncodingFormat.Base64` or `(System.Single)TextEncodingFormat.Base64` or `(float)TextEncodingFormat.Base64`)  |
|                        | `Double` (e.g. `(Double)TextEncodingFormat.Base64` or `(System.Double)TextEncodingFormat.Base64` or `(double)TextEncodingFormat.Base64`)  |

## Values

### Base64

| | |
|-|-|
| **Name:**    | Base64                                         |
| **Value:**   | [Int32][] with value `0`                       |
| **Notes:**   | Base64 encoding format. |

### URL

| | |
|-|-|
| **Name:**    | URL                                                |
| **Value:**   | [Int32][] with value `1`                           |
| **Notes:**   | URL encoding format. |

### Hex

| | |
|-|-|
| **Name:**    | Hex                                             |
| **Value:**   | [Int32][] with value `2`                        |
| **Notes:**   | Hex (Hexadecimal) encoding format. |

### HTML

| | |
|-|-|
| **Name:**    | HTML                                           |
| **Value:**   | [Int32][] with value `3`                       |
| **Notes:**   | HTML encoding format. |

### UTF8

| | |
|-|-|
| **Name:**    | UTF8                                           |
| **Value:**   | [Int32][] with value `4`                       |
| **Notes:**   | UTF8 encoding format. |

### Base64URL

| | |
|-|-|
| **Name:**    | Base64URL                                      |
| **Value:**   | [Int32][] with value `5`                       |
| **Notes:**   | Base64URL encoding format.|

## Remarks

### Creating a TextEncodingFormat

The following table shows some of the ways that `TextEncodingFormat` can be created using the expression editor (examples are for Base64 and Hex but can be applied to any of the values above by replacing the relevant values).

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use an `TextEncodingFormat` expression | `TextEncodingFormat.Base64` | `TextEncodingFormat.Base64`| Expression | Used when encoding to Base64.|
| | `TextEncodingFormat.Hex` | `TextEncodingFormat.Hex`| Expression | Used when encoding to Hex. |
| Use [Explicit Casting][] | `(TextEncodingFormat)0` | `TextEncodingFormat.Base64`| Expression | Used when encoding to Base64. |
| | `(TextEncodingFormat)2` | `TextEncodingFormat.Hex`| Expression | Used when encoding to Hex. |
| Use `Enum.Parse` | `(TextEncodingFormat)Enum.Parse(typeof(TextEncodingFormat), "Base64")` | `TextEncodingFormat.Base64`| Expression | Parses `"Base64"` and converts it to `TextEncodingFormat.Base64`. See [Enum.Parse][] |
| | `(TextEncodingFormat)Enum.Parse(typeof(TextEncodingFormat), "Hex")` | `TextEncodingFormat.Hex`| Expression | Parses `"Hex"` and converts it to `TextEncodingFormat.Hex`. See [Enum.Parse][] |
| Use `Enum.ToObject` | `(TextEncodingFormat)Enum.ToObject(typeof(TextEncodingFormat), 0)` | `TextEncodingFormat.Base64`| Expression | Converts `0` to `TextEncodingFormat.Base64` value. See [Enum.ToObject][] |
| | `(TextEncodingFormat)Enum.ToObject(typeof(TextEncodingFormat), 2)` | `TextEncodingFormat.Hex`| Expression | Converts `2` to `TextEncodingFormat.Hex` value. See [Enum.ToObject][] |

Please see [Instantiating an enumeration type][] for further information.

### Convert TextEncodingFormat to Text

The following table shows some of the ways that a `TextEncodingFormat` can be converted to text.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `TextEncodingFormat.Base64.ToString()` | `"Base64"` | Expression | Converts `TextEncodingFormat.Base64` to `"Base64"`. See [Enum.ToString][] |
| | `TextEncodingFormat.Hex.ToString()` | `"Hex"` | Expression | Converts `TextEncodingFormat.Hex` to `"Hex"`. See [Enum.ToString][] |
| Use `Convert.ToString` | `Convert.ToString(TextEncodingFormat.Base64)` | `"Base64"` | Expression | Converts `TextEncodingFormat.Base64` to `"Base64"`. See [Convert.ToString][] |
| | `Convert.ToString(TextEncodingFormat.Hex)` | `"Hex"` | Expression | Converts `TextEncodingFormat.Hex` to `"Hex"`. See [Convert.ToString][] |
| Use `Convert Object To Text` block | where `Object` property has a value of `TextEncodingFormat.Base64` | `"Base64"` | N/A  | Converts `TextEncodingFormat.Base64` to `"Base64"`. See [Convert Object To Text][] |
| | where `Object` property has a value of `TextEncodingFormat.Hex` | `"Hex"` | N/A  | Converts `TextEncodingFormat.Hex` to `"Hex"`. See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `TextEncodingFormat.Base64` | `"0"` | N/A  | Converts `TextEncodingFormat.Base64` to `"0"`. See [Convert Object To Json][] |
| | where `Object` property has a value of `TextEncodingFormat.Hex` | `"2"` | N/A  | Converts `TextEncodingFormat.Hex` to `"2"`. See [Convert Object To Json][] |

Please see [Formatting enumeration values][] for further information.

### Convert TextEncodingFormat to a Number

The following table shows some of the ways that a `TextEncodingFormat` can be converted to a number.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use [Explicit Casting][]              | `(Int32)TextEncodingFormat.Base64`   | `0` | Expression | [Casts][Explicit Casting] `TextEncodingFormat.Base64` to `0` |
|                                       | `(Int32)TextEncodingFormat.Hex`   | `2` | Expression | [Casts][Explicit Casting] `TextEncodingFormat.Hex` to `2` |
| Use `Convert.ToInt32`                 | `Convert.ToInt32(TextEncodingFormat.Base64)`   | `0` | Expression | Converts `TextEncodingFormat.Base64` to `0`. See [Convert.ToInt32][] |
|                                       | `Convert.ToInt32(TextEncodingFormat.Hex)`   | `2` | Expression | Converts `TextEncodingFormat.Hex` to `2`. See [Convert.ToInt32][] |

## See Also

### Property Editor Support

- The Expression Editor is available for [Input][] properties where the data type is `TextEncodingFormat`.
- The Literal Editor is available for [Input][] properties where the data type is `TextEncodingFormat`.
- The Variable Editor is available for [Input][], [InputOutput][] and [Output][] properties where the data type is `TextEncodingFormat`.

### Related Blocks

- [Encode Text][]
- [Decode Text][]

### Related Data Types

- [Int32][]
- [String][]

### Related Concepts

- [Explicit Casting][]
- [Working with Enums][]

[Decode Text]: {{< url "Cortex.Reference.Blocks.Text.DecodeText.DecodeText.MainDoc" >}}
[Encode Text]: {{< url "Cortex.Reference.Blocks.Text.EncodeText.EncodeText.MainDoc" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
[Working with Enums]: {{< url "Cortex.Reference.Concepts.WorkingWith.Enums.MainDoc" >}}
[Explicit Casting]: {{< url "Cortex.Reference.Concepts.WorkingWith.Objects.ObjectCasting.ExplicitCast" >}}
[Enum.Parse]: {{< url "MSDocs.DotNet.Api.System.Enum.Parse" >}}
[Enum.ToObject]: {{< url "MSDocs.DotNet.Api.System.Enum.ToObject" >}}
[Enum.ToString]: {{< url "MSDocs.DotNet.Api.System.Enum.ToString" >}}
[Convert.ToInt32]: {{< url "MSDocs.DotNet.Api.System.Convert.ToInt32" >}}
[Convert.ToString]: {{< url "MSDocs.DotNet.Api.System.Convert.ToString" >}}
[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}

[Instantiating an enumeration type]: {{< url "MSDocs.DotNet.Api.System.Enum.InstantiatingAnEnum" >}}
[Formatting enumeration values]: {{< url "MSDocs.DotNet.Api.System.Enum.FormattingEnumerationValues" >}}
