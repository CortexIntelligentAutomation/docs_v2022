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

### ServerDetails

The [ServerDetails][] are used to configure the SMTP server host and port to connect to as well as whether the connection is SSL-wrapped or not.

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
| Use a `BasicEmailSessionDetails` constructor | `new BasicEmailSessionDetails(serverDetails: new ServerDetails("host", 587, false), credentials: new UserCredentials("username", "encryptedPassword"))` | `{"ServerDetails": {"Host": "host", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "username", "Password": "encryptedPassword"}}` | Expression | N/A |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Literal Editor is available for [Input][] properties where the data type is `BasicEmailSessionDetails`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `BasicEmailSessionDetails`.

A `BasicEmailSessionDetails` can also be created using the Literal Editor by filling in the necessary values for the following properties:

| Property | Data Type | Example | Notes |
|-|-|-|-|
| `ServerDetails` | `ServerDetails` | Host: `host`<br>Port: `587`<br>UseSsl: `false` | The [ServerDetails][ServerDetails Property] that are used to connect to the server. |
| `Credentials` | `UserCredentials` | Domain: `"domain"`<br>Username: `"username"`<br>Password: `"encryptedPassword"` | The [Credentials][Credentials Property] that are used for authentication on the server. |

### Convert BasicEmailSessionDetails to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)BasicEmailSessionDetails.ToString()` | `"Cortex.DataTypes.Email.BasicEmailSessionDetails"` | Expression | ToString will return the Full Name of the BasicEmailSessionDetails Data Type |
| Use `Convert Object To Text` block | where `Object` property has a value of `{"ServerDetails": {"Host": "host", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "username", "Password": "encryptedPassword"}}` | `"Cortex.DataTypes.Email.BasicEmailSessionDetails"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `{"ServerDetails": {"Host": "host", "Port": 587, "UseSsl": false}, "Credentials": {"Domain": null, "Username": "username", "Password": "encryptedPassword"}}` | `"{\r\n  \"ServerDetails\": {\r\n    \"Host\": \"host\",\r\n    \"Port\": 587,\r\n    \"UseSsl\": false\r\n  },\r\n  \"Credentials\": {\r\n    \"Domain\": null,\r\n    \"Username\": \"username\",\r\n    \"Password\": \"encryptedPassword\"\r\n  }\r\n}"` | N/A  | See [Convert Object To Json][] |

### Known Limitations

* Currently emails cannot be sent using this data type if credentials are not provided.

* Currently, if the `ToString()` method is used on a BasicEmailSessionDetails, then its Full Name will be returned; instead of a representation of the data within the BasicEmailSessionDetails. In future this limitation may be removed.

## See Also

### Related Data Types

* [UserCredentials][]
* [ServerDetails][]

[ServerDetails Property]: {{< ref "#serverdetails" >}}
[Credentials Property]: {{< ref "#credentials" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}

[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
