---
title: "TextDecodingException"
linkTitle: "TextDecodingException"
description: "The exception thrown when an error occur while decoding text."
---

# {{% param title %}}

<p class="namespace">(Cortex.Exceptions.Text.Encode.TextDecodingException)</p>

## Description

The exception thrown when an error occurs while decoding text.

There are multiple reasons that this exception can be thrown:

- [Invalid Base64 Character][InvalidBase64Character]
- [Odd number of characters using Hex][OddHexCharacters]
- [Invalid Base64URL Character][InvalidBase64URLCharacter]

## Reasons

### Invalid Base64 Character {#100}

#### Message Format

```json
"An error occured during decoding due to an invalid character being present.
Please click the HelpLink for more information on how to fix this."
```

#### How to fix

Provide a [String][] containing only valid characters e.g. `A–Z` , `a–z` , `0–9` , `+` , `/` and `=`. 

### Odd number of characters using Hex {#300}

#### Message Format

```json
"An error occured during decoding due to an odd number of characters being present.
Please click the HelpLink for more information on how to fix this."
```

#### How to fix

Provide a [String][] containing an even number of characters.

### Invalid Base64URL Character {#600}

#### Message Format

```json
"An error occured during decoding due to an invalid character being present.
Please click the HelpLink for more information on how to fix this."
```

#### How to fix

Provide a [String][] containing only valid characters e.g. `A–Z` , `a–z` , `0–9` , `+` , `/` and `=`.

## Properties

### Exception Type

The type of the exception (i.e. `TextDecodingException`)

| | |
|-----------|------------|
| Data Type | [String][] |

### Message

The exception message, providing information about the exception that occurred.

| | |
|-----------|------------|
| Data Type | [String][] |

### Category

The category of the exception, which is used to categorise an exception if there are multiple reasons that the exception can occur.

For `TextDecodingException` there are the following categories:

- `Base64`
- `Hex`
- `Base64URL`

| | |
|-----------|------------|
| Data Type | [String][] |

### Error Code

The error code for the exception, which is used to indicate the reason that the exception occurred, if there are multiple reasons that the exception can occur.

For `TextEncodingException` there are the following error codes:

- [100][InvalidBase64Character] - Indicates that the provided [String][] to decode contains an invalid character
- [300][OddHexCharacters] - Indicates that the provided [String][] to decode contains an odd number of characters meaning it is not valid
- [600][InvalidBase64URLCharacter] - Indicates that the provided [String][] to decode contains an invalid character

| | |
|-----------|---------------------------|
| Data Type | [TextDecodingErrorCode][] |

### Help Link

The URL for the relevant section of this exception's help page.

| | |
|-----------|------------|
| Data Type | [String][] |

## Remarks

### Known Limitations

None

## See Also

### Related Data Types

* [String][]

### Related Concepts

* [Exceptions][]

### Related Blocks

* [Decode Text][]

### External Documentation

None

[Decode Text]: {{< url "Cortex.Reference.Blocks.Text.DecodeText.DecodeText.MainDoc" >}}
[InvalidBase64Character]: {{< ref "#100">}}
[OddHexCharacters]: {{< ref "#300">}}
[InvalidBase64URLCharacter]: {{< ref "#600">}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}

[TextDecodingErrorCode]: {{< url "Cortex.Reference.DataTypes.Text.TextDecodingErrorCode.MainDoc" >}}

[Exceptions]: {{< url "Cortex.Reference.Concepts.Fundamentals.Exceptions.MainDoc" >}}
