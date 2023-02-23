---
title: "StringSplitOptions"
linkTitle: "StringSplitOptions"
description: "Used to specify settings for splitting text (i.e. whether to include or remove empty entries from results)."
---

# {{% param title %}}

<p class="namespace">(System.StringSplitOptions)</p>

## Summary

Specifies settings for splitting text to manipulate whitespaces in resulting text.

| | |
|-|-|
| **Category:**          | Text                                                     |
| **Name:**              | `StringSplitOptions`                                     |
| **Full Name:**         | `System.StringSplitOptions`                              |
| **Alias:**             | N/A                                                      |
| **Description:**       | StringSplitOptions defines the formatting of the resulting list when using string.split. |
| **Size:**              | `4` bytes                                              |
| **Default Value:**     | `(StringSplitOptions)0`                             |
| **Can be used as:**    | `StringSplitOptions`, `Object`, `dynamic`           |
| **Can be cast to:**    | `Int16` (e.g. `(Int16)StringSplitOptions.None` or `(System.Int16)StringSplitOptions.None` or `(short)StringSplitOptions.None`)  |
|                        | `Int32` (e.g. `(Int32)StringSplitOptions.None` or `(System.Int32)StringSplitOptions.None` or `(int)StringSplitOptions.None`)  |
|                        | `Int64` (e.g. `(Int64)StringSplitOptions.None` or `(System.Int64)StringSplitOptions.None` or `(long)StringSplitOptions.None`)  |
|                        | `Single` (e.g. `(Single)StringSplitOptions.None` or `(System.Single)StringSplitOptions.None` or `(float)StringSplitOptions.None`)  |
|                        | `Double` (e.g. `(Double)StringSplitOptions.None` or `(System.Double)StringSplitOptions.None` or `(double)StringSplitOptions.None`)  |

## Values

### None

| | |
|-|-|
| **Name:**    | None                                           |
| **Value:**   | [Int32][] with value `0`                       |
| **Notes:**   | Empty entries are not removed.                 |

### RemoveEmptyEntries

| | |
|-|-|
| **Name:**    | RemoveEmptyEntries                                         |
| **Value:**   | [Int32][] with value `1`                                   |
| **Notes:**   | Empty entries are removed.                                 |

### Trim Entries

| | |
|-|-|
| **Name:**    | TrimEntries                                                                                |
| **Value:**   | [Int32][] with value `2`                                                                   |
| **Notes:**   | Empty entries are not removed but trailing or leading whitespaces (at the end or start of a string) are removed.  |

## Remarks

### Create StringSplitOptions

The following table shows some of the ways that `StringSplitOptions` can be created using the expression editor.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `StringSplitOptions` expression | `StringSplitOptions.None` | `StringSplitOptions.None`| Expression | Empty entries are not removed.|
| | `StringSplitOptions.RemoveEmptyEntries` | `StringSplitOptions.RemoveEmptyEntries`| Expression | Empty Entries are removed. |
| | `StringSplitOptions.TrimEntries` | `StringSplitOptions.TrimEntries`| Expression | Used when encoding to TrimEntries. |
| Use [Explicit Casting][] | `(StringSplitOptions)0` | `StringSplitOptions.None`| Expression | Empty entries are not removed. |
| | `(StringSplitOptions)1` | `StringSplitOptions.RemoveEmptyEntries`| Expression | Empty entries are removed. |
| | `(StringSplitOptions)2` | `StringSplitOptions.TrimEntries`| Expression | Used when encoding to TrimEntries. |
| Use `Enum.Parse` | `(StringSplitOptions)Enum.Parse(typeof(StringSplitOptions), "None")` | `StringSplitOptions.None`| Expression | Parses `"None"` and converts it to `StringSplitOptions.None`. See [Enum.Parse][] |
| | `(StringSplitOptions)Enum.Parse(typeof(StringSplitOptions), "RemoveEmptyEntries")` | `StringSplitOptions.RemoveEmptyEntries`| Expression | Parses `"RemoveEmptyEntries"` and converts it to `StringSplitOptions.RemoveEmptyEntries`. See [Enum.Parse][] |
| | `(StringSplitOptions)Enum.Parse(typeof(StringSplitOptions), "TrimEntries")` | `StringSplitOptions.TrimEntries`| Expression | Parses `"TrimEntries"` and converts it to `StringSplitOptions.TrimEntries`. See [Enum.Parse][] |
| Use `Enum.ToObject` | `(StringSplitOptions)Enum.ToObject(typeof(StringSplitOptions), 0)` | `StringSplitOptions.None`| Expression | Converts `0` to `StringSplitOptions.None` value. See [Enum.ToObject][] |
| | `(StringSplitOptions)Enum.ToObject(typeof(StringSplitOptions), 1)` | `StringSplitOptions.RemoveEmptyEntries`| Expression | Converts `2` to `StringSplitOptions.RemoveEmptyEntries` value. See [Enum.ToObject][] |
| | `(StringSplitOptions)Enum.ToObject(typeof(StringSplitOptions), 2)` | `StringSplitOptions.TrimEntries`| Expression | Converts `2` to `StringSplitOptions.TrimEntries` value. See [Enum.ToObject][] |

Please see [Instantiating an enumeration type][] for further information.

### Convert StringSplitOptions to Text

The following table shows some of the ways that a `StringSplitOptions` can be converted to text.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `StringSplitOptions.None.ToString()` | `"None"` | Expression | Converts `StringSplitOptions.None` to `"None"`. See [Enum.ToString][] |
| | `StringSplitOptions.RemoveEmptyEntries.ToString()` | `"RemoveEmptyEntries"` | Expression | Converts `StringSplitOptions.RemoveEmptyEntries` to `"RemoveEmptyEntries"`. See [Enum.ToString][] |
| | `StringSplitOptions.TrimEntries.ToString()` | `"TrimEntries"` | Expression | Converts `StringSplitOptions.TrimEntries` to `"TrimEntries"`. See [Enum.ToString][] |
| Use `Convert.ToString` | `Convert.ToString(StringSplitOptions.None)` | `"None"` | Expression | Converts `StringSplitOptions.None` to `"None"`. See [Convert.ToString][] |
| | `Convert.ToString(StringSplitOptions.RemoveEmptyEntries)` | `"RemoveEmptyEntries"` | Expression | Converts `StringSplitOptions.RemoveEmptyEntries` to `"RemoveEmptyEntries"`. See [Convert.ToString][] |
| | `Convert.ToString(StringSplitOptions.TrimEntries)` | `"TrimEntries"` | Expression | Converts `StringSplitOptions.TrimEntries` to `"TrimEntries"`. See [Convert.ToString][] |
| Use `Convert Object To Text` block | where `Object` property has a value of `StringSplitOptions.None` | `"None"` | N/A  | Converts `StringSplitOptions.None` to `"None"`. See [Convert Object To Text][] |
| | where `Object` property has a value of `StringSplitOptions.RemoveEmptyEntries` | `"RemoveEmptyEntries"` | N/A  | Converts `StringSplitOptions.RemoveEmptyEntries` to `"RemoveEmptyEntries"`. See [Convert Object To Text][] |
| | where `Object` property has a value of `StringSplitOptions.TrimEntries` | `"TrimEntries"` | N/A  | Converts `StringSplitOptions.TrimEntries` to `"TrimEntries"`. See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `StringSplitOptions.None` | `"0"` | N/A  | Converts `StringSplitOptions.None` to `"0"`. See [Convert Object To Json][] |
| | where `Object` property has a value of `StringSplitOptions.RemoveEmptyEntries` | `"1"` | N/A  | Converts `StringSplitOptions.RemoveEmptyEntries` to `"1"`. See [Convert Object To Json][] |
| | where `Object` property has a value of `StringSplitOptions.TrimEntries` | `"2"` | N/A  | Converts `StringSplitOptions.TrimEntries` to `"2"`. See [Convert Object To Json][] |

Please see [Formatting enumeration values][] for further information.

### Convert StringSplitOptions to a Number

The following table shows some of the ways that an `StringSplitOptions` can be converted to a number.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use [Explicit Casting][]              | `(Int32)StringSplitOptions.None`   | `0` | Expression | [Casts][Explicit Casting] `StringSplitOptions.None` to `0` |
|                                       | `(Int32)StringSplitOptions.RemoveEmptyEntries`   | `1` | Expression | [Casts][Explicit Casting] `StringSplitOptions.RemoveEmptyEntries` to `1` |
|                                       | `(Int32)StringSplitOptions.TrimEntries`   | `2` | Expression | [Casts][Explicit Casting] `StringSplitOptions.TrimEntries` to `2` |
| Use `Convert.ToInt32`                 | `Convert.ToInt32(StringSplitOptions.None)`   | `0` | Expression | Converts `StringSplitOptions.None` to `0`. See [Convert.ToInt32][] |
|                                       | `Convert.ToInt32(StringSplitOptions.RemoveEmptyEntries)`   | `1` | Expression | Converts `StringSplitOptions.RemoveEmptyEntries` to `1`. See [Convert.ToInt32][] |
|                                       | `Convert.ToInt32(StringSplitOptions.TrimEntries)`   | `2` | Expression | Converts `StringSplitOptions.TrimEntries` to `2`. See [Convert.ToInt32][] |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `StringSplitOptions`.
* The Literal Editor is available for [Input][] properties where the data type is `StringSplitOptions`.
* The Variable Editor is available for [Input][], [InputOutput][] and [Output][] properties where the data type is `StringSplitOptions`.

### Known Limitations

Currently only possible to both trim text and remove empty whitespaces in the expression editor by using `(StringSplitOptions)3`.

## See Also

### Related Blocks

* [Split Text][]

### Related Data Types

* [Int32][]
* [String][]

### Related Concepts

* [Explicit Casting][]
* [Working with Enums][]

### External Documentation

[Split Text]: {{< url "Cortex.Reference.Blocks.Text.SplitText.SplitText.MainDoc" >}}

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
