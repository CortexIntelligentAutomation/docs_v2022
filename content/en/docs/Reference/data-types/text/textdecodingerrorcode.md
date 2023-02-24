---
title: "TextDecodingErrorCode"
linkTitle: "TextDecodingErrorCode"
description: "Used to represent an error code explaining the reason an `TextDecodingException` occurred."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Text.Encode.TextDecodingErrorCode)</p>

## Summary

The `TextDecodingErrorCode` data type is used to represent an error code explaining the reason a [TextDecodingException][] occurred. For more information on the exception itself, see [TextDecodingException][].

`TextDecodingErrorCode` is an [enum][Working with Enums] data type, which means it has a defined set of values, where each value has an associated [String][] name and [Int32][] value.

## Values

### Base64InvalidCharacter

| | |
|-|-|
| **Name:**    | Base64InvalidCharacter                                     |
| **Value:**   | [Int32][] with value `100`                      |
| **Notes:**   | Used when an [TextDecodingException][] occured due to provided text containing an invalid character. See [Invalid Base64 Character][InvalidBase64]. |

### HexOddNumberOfCharacters

| | |
|-|-|
| **Name:**    | HexOddNumberOfCharacters                                     |
| **Value:**   | [Int32][] with value `300`                      |
| **Notes:**   | Used when an [TextDecodingException][] occured due to provided text containing an odd number of characters. See [Odd number of characters using Hex][InvalidHex]. |

### Base64URLInvalidCharacter

| | |
|-|-|
| **Name:**    | Base64URLInvalidCharacter                                    |
| **Value:**   | [Int32][] with value `600`                      |
| **Notes:**   | Used when an [TextDecodingException][] occured due to provided text containing an invalid character. See [Invalid Base64URL Character][InvalidBase64URL]. |

[TextDecodingException]: {{< url "Cortex.Reference.Exceptions.Text.Encode.TextDecodingException.MainDoc" >}}
[InvalidBase64]: {{< url "Cortex.Reference.Exceptions.Text.Encode.TextDecodingException.InvalidBase64" >}}
[InvalidHex]: {{< url "Cortex.Reference.Exceptions.Text.Encode.TextDecodingException.InvalidHex" >}}
[InvalidBase64URL]: {{< url "Cortex.Reference.Exceptions.Text.Encode.TextDecodingException.InvalidBase64URL" >}}

[Working with Enums]: {{< url "Cortex.Reference.Concepts.WorkingWith.Enums.MainDoc" >}}
[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}
