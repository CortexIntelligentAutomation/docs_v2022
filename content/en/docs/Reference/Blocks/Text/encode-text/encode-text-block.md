---
title: "Encode Text"
linkTitle: "Encode Text"
description: "Encodes text to a specified format (e.g. `\"base64\"`)."
---

{{< figure src="/blocks/text-encode-text-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Text.Encode.EncodeTextBlock)</p>

## Description

Converts [Text][Text Property] to a specified format.

## Examples

### Text Encoded to Base64

This example will convert `"The quick brown fox jumps over the lazy dog"` to Base64.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The quick brown fox jumps over the lazy dog"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `Base64` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"The quick brown fox jumps over the lazy dog"` to Base64 will result in the variable `($)Text` being updated to the following:

```json
"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="
```

### Text Encoded to Hex

This example will convert `"The quick brown fox jumps over the lazy dog"` to Hex.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The quick brown fox jumps over the lazy dog"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `Hex` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"The quick brown fox jumps over the lazy dog"` to Hex will result in the variable `($)Text` being updated to the following:

```json
"54686520717569636b2062726f776e20666f78206a756d7073206f76657220746865206c617a7920646f67"
```

### Text Encoded to HTML

This example will convert `"¡The quick brown fox jumps over the lazy dog!<>"` to HTML.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The quick brown fox jumps over the lazy dog"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `HTML` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"The quick brown fox jumps over the lazy dog"` to HTML will result in the variable `($)Text` being updated to the following:

```json
"&iexcl;The quick brown fox jumps over the lazy dog!&lt;&gt;"
```

***

## Properties

### Text

The [Text][Text Property] to Encode to the specified format.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)Text` with no value |

### Format

The [Format][Format Property] used to perform the encoding of the [Text][Text Property].

| | |
|--------------------|---------------------------|
| Data Type | [TextEncodingFormat][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | `Base64` |

## Exceptions

The exceptions thrown by the block can be found below:

| Name     | Description |
|----------|----------|
| [ArgumentException][] | Thrown when the format is not one of the specified [Format][Format Property] types (e.g. `(TextEncodingFormat)10`). |

## Remarks

### Encoding to Base64

When Encoding to base64 a new line character is added every 76 characters

### Null or empty Text

If [Text][Text Property] is `null` or empty (i.e. `""`), no operation is performed.

[Text Property]: {{< ref "#text" >}}
[Format Property]: {{< ref "#format" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[TextEncodingFormat]: {{< url "Cortex.Reference.DataTypes.Text.TextEncodingFormat.MainDoc" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}

[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
