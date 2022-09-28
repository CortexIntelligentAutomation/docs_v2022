---
title: "BasicEmailSessionDetails"
linkTitle: "BasicEmailSessionDetails"
description: "Used when opening a session with an SMTP server."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.BasicEmailSessionDetails)</p>

## Summary

The `BasicEmailSessionDetails` data type is used when opening a session with an SMTP server.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `BasicEmailSessionDetails`                             |
| **Full Name:**         | `Cortex.DataTypes.Email.BasicEmailSessionDetails`      |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type representing configuration for opening a session with an SMTP server. |
| **Default Value:**     | null                                                   |
| **Can be used as:**    | `BasicEmailSessionDetails`, `Object`, `dynamic`        |
| **Can be cast to:**    | N/A                                                    |

### Properties

### Server Details

The Server Details are used to configure the SMTP server host and port to connect to as well as whether the connection is SSL-wrapped or not.

| | |
|--------------------|---------------------------|
| Data Type | [ServerDetails][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | `null` |

### Credentials

The Credentials are used for SMTP Authentication.

| | |
|--------------------|---------------------------|
| Data Type | [UserCredentials][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | `null` |

## Remarks

### Create a BasicEmailSessionDetails

The following table shows some of the ways that `BasicEmailSessionDetails` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `BasicEmailSessionDetails` constructor | `new BasicEmailSessionDetails(new ServerDetails("host", 587, false), new UserCredentials("username", "encryptedPassword"))` | `{"ServerDetails": {"Host": "host", "Port": 587, "UseSsl": false}, "Credentials": {"Username": "username", "Password": "encryptedPassword"}}` | Expression |  |

### Property Editor Support

* The Expression Editor is not available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Literal Editor is not available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `BasicEmailSessionDetails`.
  
### Known Limitations

* Currently emails cannot be sent using this data type if credentials are not provided.

## See Also

### Related Data Types

* [UserCredentials][]
* [ServerDetails][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
