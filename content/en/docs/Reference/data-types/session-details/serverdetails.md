---
title: "ServerDetails"
linkTitle: "ServerDetails"
description: "The data type representing configuration for establishing and maintaining a connection/session with a server."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.SessionDetails.ServerDetails)</p>

## Summary

The `ServerDetails` data type is used to establish and maintain a session/connection with a server.

| | |
|-|-|
| **Category:**          | Session Details                                        |
| **Name:**              | `ServerDetails`                                        |
| **Full Name:**         | `Cortex.DataTypes.SessionDetails.ServerDetails`        |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type representing configuration for establishing and maintaining a connection/session with a server. |
| **Default Value:**     | null                                                   |
| **Can be used as:**    | `ServerDetails`, `Object`, `dynamic`                   |
| **Can be cast to:**    | N/A                                                    |

## Properties

### Host

The Host is used to define the server address with which a session/connection should be opened.

| | |
|--------------------|---------------------------|
| Data Type | [EncryptableText][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [EncryptableText][] with value `""` |

### Port

The Port is used to define the server port with which a session/connection should be opened on the [Host][Host Property].

| | |
|--------------------|---------------------------|
| Data Type | [Int32][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [Int32][] with value `0` |

### UseSsl

UseSsl is used to define whether or not the connection should be SSL-wrapped or not. Setting this to `false` does not necessarily mean that SSL will not be used, if the server supports the STARTTLS extension, SSL may still be used.

| | |
|--------------------|---------------------------|
| Data Type | [Boolean][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [Boolean][] with value `true` |

## Remarks

### Create a ServerDetails

The following table shows some of the ways that `ServerDetails` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `ServerDetails` constructor | `new ServerDetails(host: "host", port: 465, useSsl: true)` | `{"Host": "host", "Port": 465, "UseSsl": true}` | Expression |  |

A `ServerDetails` can also be created using the Literal Editor by filling in the necessary values for the following properties:

| Property | Data Type | Example | Notes |
|-|-|-|-|
| `Host` | `EncryptableText` | `"host"` | The server address of the [Host][Host Property]. |
| `Port` | `Int32` | `465` | The [Port][Port Property] on the server address on which the session/connection should be opened. |
| `UseSsl` | `Boolean` | `true` | The [Boolean][] used to determine whether or not an SSL-wrapped connection should be made. |

### Convert ServerDetails to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)ServerDetails.ToString()` | `"Cortex.DataTypes.SessionDetails.ServerDetails"` | Expression | ToString will return the Full Name of the ServerDetails Data Type |
| Use `Convert Object To Text` block | where `Object` property has a value of `{"Host": "host", "Port": 465, "UseSsl": true}` | `"Cortex.DataTypes.SessionDetails.ServerDetails"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `{"Host": "host", "Port": 465, "UseSsl": true}` | `"{\r\n  \"Host\": \"host\",\r\n  \"Port\": 465,\r\n  \"UseSsl\": true\r\n}"` | N/A  | See [Convert Object To Json][] |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `ServerDetails`.
* The Literal Editor is available for [Input][] properties where the data type is `ServerDetails`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `ServerDetails`.
  
### Known Limitations

Currently, if the `ToString()` method is used on a ServerDetails, then its Full Name will be returned; instead of a representation of the data within the ServerDetails.

In future this limitation may be removed.

## See Also

### Related Data Types

* [BasicEmailSessionDetails][]
* [EncryptableText][]

[Host Property]: {{< ref "#host" >}}
[Port Property]: {{< ref "#port" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}

[EncryptableText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptableText.MainDoc" >}}
[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}
[Boolean]: {{< url "Cortex.Reference.DataTypes.ConditionalLogic.Boolean.MainDoc" >}}

[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
