---
title: "ServerDetails"
linkTitle: "ServerDetails"
description: "Used when opening a session/connection with a server."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.SessionDetails.ServerDetails)</p>

## Summary

The `ServerDetails` data type is used when opening a session/connection with a server.

| | |
|-|-|
| **Category:**          | Session Details                                        |
| **Name:**              | `ServerDetails`                                        |
| **Full Name:**         | `Cortex.DataTypes.SessionDetails.ServerDetails`        |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type representing configuration for opening a session/connection with a server. |
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

UseSsl is used to define whether or not the connection should be SSL-wrapped or not. Setting this to `false` does not necessarily mean that SSL will not be used, if the mail server supports the STARTTLS extension, SSL may still be used.

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
| Use a `ServerDetails` constructor | `new ServerDetails("host", 465, true)` | `{"Host": "host", "Port": 465, "UseSsl": true}` | Expression |  |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `ServerDetails`.
* The Literal Editor is available for [Input][] properties where the data type is `ServerDetails`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `ServerDetails`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [BasicEmailSessionDetails][]
* [EncryptableText][]

[Host Property]: {{< ref "#host" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}

[EncryptableText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptableText.MainDoc" >}}
[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}
[Boolean]: {{< url "Cortex.Reference.DataTypes.ConditionalLogic.Boolean.MainDoc" >}}
