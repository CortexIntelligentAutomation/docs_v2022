---
title: "BasicEmailSessionDetails"
linkTitle: "BasicEmailSessionDetails"
description: "The data type representing configuration for establishing and maintaining a session with a mail server."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.BasicEmailSessionDetails)</p>

## Summary

The `BasicEmailSessionDetails` data type is used to open and maintain a session with a mail server.

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `BasicEmailSessionDetails`                             |
| **Full Name:**         | `Cortex.DataTypes.Email.BasicEmailSessionDetails`      |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type representing configuration for opening and maintaining a session with a mail server. |
| **Default Value:**     | null                                                   |
| **Can be used as:**    | `BasicEmailSessionDetails`, `Object`, `dynamic`        |
| **Can be cast to:**    | N/A                                                    |

## Properties

### Server Details

The Server Details are used to configure the SMTP server host and port to connect to as well as whether the connection is SSL-wrapped or not.

| | |
|--------------------|---------------------------|
| Data Type | [ServerDetails][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [ServerDetails][] with value:<br>Host: `""`<br>Port: `465`<br>UseSsl: `true` |

### Credentials

The Credentials are used for SMTP Authentication.

| | |
|--------------------|---------------------------|
| Data Type | [UserCredentials][] |
| Is Advanced | `false` |
| Default Editor | [Literal][] |
| Default Value | [UserCredentials][] with value:<br>Domain: `""`<br>Username: `""`<br>Password: `""` |

## Remarks

### Create a BasicEmailSessionDetails

The following table shows some of the ways that `BasicEmailSessionDetails` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `BasicEmailSessionDetails` constructor | `new BasicEmailSessionDetails(new ServerDetails("host", 587, false), new UserCredentials("username", "encryptedPassword"))` | `{"ServerDetails": {"Host": "host", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "username", "Password": "encryptedPassword"}}` | Expression |  |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Literal Editor is available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `BasicEmailSessionDetails`.

A `BasicEmailSessionDetails` can also be created using the Literal Editor by filling in the necessary values for the following properties:

...

### Known Limitations

* Currently emails cannot be sent using this data type if credentials are not provided.

## See Also

### Related Data Types

* [UserCredentials][]
* [ServerDetails][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
