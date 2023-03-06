---
title: "Encode Text"
linkTitle: "Encode Text"
description: "Encodes text to a specified format (e.g. `\"Base64\"`)."
---

{{< figure src="/blocks/text-encode-text-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Text.EncodeText.EncodeTextBlock)</p>

## Description

Encodes [Text][Text Property] to a specified [Format][Format Property].

## Examples

### Text encoded to Base64

This example will encode the [Text][Text Property] `"The quick brown fox jumps over the lazy dog"` to [Base64][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The quick brown fox jumps over the lazy dog"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `Base64` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"The quick brown fox jumps over the lazy dog"` to the [Format][Format Property] [Base64][] will result in the variable `($)Text` being updated to the following:

```json
"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="
```

***

### Text encoded from URL

This example will encode the [Text][Text Property] `"The quick brown fox jumps over the lazy dog!"` to [URL][]. to `"The quick brown fox jumps over the lazy dog!"`.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The%20quick%20brown%20fox%20jumps%20over%20the%20lazy%20dog%21"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `"TextEncodingFormat.URL"` | `($)Format` is a variable of type [TextEncodingFormat][]

#### Result

Encoding `"The%20quick%20brown%20fox%20jumps%20over%20the%20lazy%20dog%21"` to the [Format][Format Property] [URL] will result in the variable `($)Text` being updated to the following:

```json
"The%20quick%20brown%20fox%20jumps%20over%20the%20lazy%20dog%21"
```

***

### Text encoded to Hex

This example will encode the [Text][Text Property] `"The quick brown fox jumps over the lazy dog"` to [Hex][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"The quick brown fox jumps over the lazy dog"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `Hex` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"The quick brown fox jumps over the lazy dog"` to the [Format][Format Property] [Hex][] will result in the variable `($)Text` being updated to the following:

```json
"54686520717569636b2062726f776e20666f78206a756d7073206f76657220746865206c617a7920646f67"
```

***

### Text encoded to HTML

This example will encode the [Text][Text Property] `"<p>The quick brown fox jumps over the lazy dog!</p>"` to [HTML][].

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"<p>The quick brown fox jumps over the lazy dog!</p>"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `HTML` | `($)Format` is a variable of type [TextEncodingFormat][] |

#### Result

Encoding `"<p>The quick brown fox jumps over the lazy dog!</p>"` to the [Format][Format Property] [HTML][] will result in the variable `($)Text` being updated to the following:

```json
"&lt;p&gt;The quick brown fox jumps over the lazy dog!&lt;/p&gt;"
```

***

## Properties

### Text

The [Text][Text Property] to Encode to the specified [Format][Format Property].

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)Text` with no value |

### Format

The [Format][Format Property] used to encode the given [Text][Text Property].

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

When Encoding to [Base64][] a new line character is added every 76 characters.

### Null or empty Text

If [Text][Text Property] is `null` or empty (i.e. `""`), no operation is performed.

### Round-Tripping

It should be possible to pass the text created by a [Decode Text][] block to this block, and then pass the text created by this block back to an [Decode Text][] block; this is called round-tripping.

### Immutable String data type

The [String][] data type used to represent [Text][Text Property] is immutable, which means it is read-only and cannot be changed once created.

To overcome this, this block creates a new [String][] which has the [Text][Text Property], encodes to [Format][Format Property] and re-assigns it to the variable specified in the [Text][Text Property] property.

[Text Property]: {{< ref "#text" >}}
[Format Property]: {{< ref "#format" >}}
[Decode Text]: {{< url "Cortex.Reference.Blocks.Text.DecodeText.DecodeText.MainDoc" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[TextEncodingFormat]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.MainDoc" >}}
[HTML]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.Html" >}}
[Base64]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.Base64" >}}
[Hex]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.Hex" >}}
[Base64URL]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.Base64URL" >}}
[URL]: {{< url "Cortex.Reference.DataTypes.Text.Encoding.TextEncodingFormat.URL" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}

[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
