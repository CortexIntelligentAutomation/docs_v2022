---
title: "Decode Text"
linkTitle: "Decode Text"
description: "Decodes the text of the given format back into text."
---

{{< figure src="/blocks/text-decode-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Text.EncodeText.DecodeTextBlock)</p>

## Description

Decodes the given text using the specified format.

## Examples

### Text decoded from Base64

This example will decode the Base64 encoded text `"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="` to `"The quick brown fox jumps over the lazy dog"`.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `"TextEncodingFormat.Base64"` | `($)Format` is a variable of type [TextEncodingFormat][]

#### Result

Decoding `"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="` with the format `Base64` results in the variable `($)Text` being updated to the following:

```json
"The quick brown fox jumps over the lazy dog"
```

***

### Text Decoding from Hex

This example will decode the Hex encoded text `"54686520717569636B2062726F776E20666F78206A756D7073206F76657220746865206C617A7920646F67"` to `"The quick brown fox jumps over the lazy dog"`.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"54686520717569636B2062726F776E20666F78206A756D7073206F76657220746865206C617A7920646F67"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `"TextEncodingFormat.Hex"` | `($)Format` is a variable of type [TextEncodingFormat][]

#### Result

Decoding `"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="` with the format `Hex` results in the variable `($)Text` being updated to the following:

```json
"The quick brown fox jumps over the lazy dog"
```

***

### Text Decoding From HTML

This example will decode the Base64 encoded text `"&#161;The quick brown fox jumps over the lazy dog!&lt;&gt;"` to `"¡The quick brown fox jumps over the lazy dog!<>"`.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Text][Text Property] | `($)Text`, with value `"&#161;The quick brown fox jumps over the lazy dog!&lt;&gt;"` | `($)Text` is a variable of type [String][] |
| [Format][Format Property] | `($)Format`, with value `"TextEncodingFormat.HTML"` | `($)Format` is a variable of type [TextEncodingFormat][]

#### Result

Decoding `"VGhlIHF1aWNrIGJyb3duIGZveCBqdW1wcyBvdmVyIHRoZSBsYXp5IGRvZw=="` with the format `HTML` results in the variable `($)Text` being updated to the following:

```json
"¡The quick brown fox jumps over the lazy dog!<>"
```

***

## Properties

### Text

The [Text][Text Property] to decode using the given [Format][Format Property] from.

| | |
|--------------------|---------------------------|
| Data Type | [String][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)Text` with no value |

### Format

The [Format][Format Property] with which the given [Text][Text Property] will be decoded using.

[Format][Format Property] can be any of the predefined values:

* `TextEncodingFormat.Base64`
* `TextEncodingFormat.URL`
* `TextEncodingFormat.Hex`
* `TextEncodingFormat.HTML`
* `TextEncodingFormat.UTF8`
* `TextEncodingFormat.Base64URL`

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
| [ArgumentException][] | Thrown when the [Format][Format Property] is not one of the specified [TextEncodingFormat][] types (e.g. `(TextEncodingFormat)10`). |
| [TextDecodingException][] | Thrown when an invalid character is provided for a Base64 decoding |
||Thrown when an odd number of characters are present in a string provided for a Hex decoding |
|| Thrown when an invalid character is present in a string provided for a Base64URL decoding |

## Remarks

### Null or empty Text

If [Text][Text Property] is `null` or empty (i.e. `""`) there is nothing to decode, so no operation is performed.

### Decoding invalid hex values

Decoding using the `Hex` [Format][Format Property] will run even if invalid characters are present but will decode incorrectly e.g. `"ZZ"` will decode to `"3"`

### Out of range URL character

When decoding using the `URL` [Format][Format Property], characters in the range `%00` to `%ff` will be treated as encoded characters but anything outside this range will be treated as a literal e.g. `"%zzExample%21"` will decide to `%zzExample!`

### Invalid HTML entity

When decoding using the `HTML` [Format][Format Property], invalid entities will be remove during decoding e.g. `"Example&something;"` will decode to `Example`

### HTML decoding ampersand

When decoding using the `HTML` [Format][Format Property], any ampersand that is not part of an entity will be removed during decoding e.g. `Example&something` will decode to `Examplesomething`

### HTML decoding semicolon

When decoding using the `HTML` [Format][Format Property], any semicolon that is not part of an entity will be treated as a literal value e.g. `Examplesomething;` will decode to `Examplesomething;`

[Text Property]: {{< ref "#text" >}}
[Format Property]: {{< ref "#format" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[TextEncodingFormat]: {{< url "Cortex.Reference.DataTypes.Text.TextEncodingFormat.MainDoc" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}

[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
