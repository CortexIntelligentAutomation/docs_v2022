---
title: "TextEncodingFormat"
linkTitle: "TextEncodingFormat"
description: "The available types of encoding format available for use with text encode and decode blocks."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Text.TextEncodingFormat)</p>

## Summary

There are currently 6 possible encoding formats for use with the text encode and decode blocks.

## Values

DECIDE WHICH FORMAT IS BETTER TABLE OR HEADING BASED

|Format|Details|
|------|-------|
|Base64|Base64 encoding format.|
|URL|URL encoding format.|
|Hex|Hex (Hexadecimal) encoding format.|
|HTML|HTML encoding format.|
|UTF8|UTF8 encoding format.|
|Base64URL|Base64URL encoding format.|

### Base64

Base64 encoding format.

### URL

URL encoding format.

### Hex

Hex (Hexadecimal) encoding format.

### HTML

HTML encoding format.

### UTF8

UTF8 encoding format.

### Base64URL

Base64URL encoding format.

## Remarks

Created in a literal editor but can be manually created in an expression editor either by using (examples for Base64)

```json
TextEncodingFormat.Base64
```

where Base64 can be replaced by one of the values shown above

or

```json
(TextEncodingFormat)0
```

where 0 can be replaced by any number from 0-5 corresponding to the list of values abov

## See Also

### Related Blocks

[Encode Text]

[Decode Text]

[Decode Text]: {{< url "Cortex.Reference.Blocks.Text.EncodeText.DecodeText.MainDoc" >}}
[Encode Text]: {{< url "Cortex.Reference.Blocks.Text.EncodeText.EncodeText.MainDoc" >}}
