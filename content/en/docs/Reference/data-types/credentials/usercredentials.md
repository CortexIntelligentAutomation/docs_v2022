---
title: "UserCredentials"
linkTitle: "UserCredentials"
description: "The data type representing configuration for authentication when establishing a connection with a server."
---


# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Credentials.UserCredentials)</p>

## Summary

The `UserCredentials` data type is used for authentication when establishing a connection with a server.

| | |
|-|-|
| **Category:**          | Credentials                                            |
| **Name:**              | `UserCredentials`                                      |
| **Full Name:**         | `Cortex.DataTypes.Credentials.UserCredentials`         |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type representing configuration for authentication when establishing a connection with a server. |
| **Default Value:**     | null                                                   |
| **Can be used as:**    | `UserCredentials`, `Object`, `dynamic`                 |
| **Can be cast to:**    | N/A                                                    |

## Properties

### Domain

The Domain is used to define the domain to be used in authentication.

| | |
|--------------------|---------------------------|
| Data Type | [EncryptableText][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [EncryptableText][] with value `""` |

### Username

The Username is used to define the username to be used in authentication.

| | |
|--------------------|---------------------------|
| Data Type | [EncryptableText][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [EncryptableText][] with value `""` |

### Password

The Password is used to define the password to be used in authentication. This property is an [EncryptedText][] and so it must be encrypted, for more information on how to encrypt the password, see [EncryptedText][].

| | |
|--------------------|---------------------------|
| Data Type | [EncryptedText][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [EncryptedText][] with value `""` |

## Exceptions

The exceptions thrown by the data type can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| [UnencryptedTextException][]         |Thrown when the [Password][Password Property] is not encrypted.|

## Remarks

### Create a UserCredentials

The following table shows some of the ways that `UserCredentials` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `UserCredentials` constructor | `new UserCredentials(domain: "domain", username: "username", password: "encryptedPassword")` | `{"Domain": "domain", "Username": "username", "Password": "encryptedPassword"}` | Expression |  |
| | `new UserCredentials(username: "username", password: "encryptedPassword")` | `{"Domain": null, "Username": "username", "Password": "encryptedPassword"}` | Expression |  |

A `UserCredentials` can also be created using the Literal Editor by filling in the necessary values for the following properties:

| Property | Data Type | Example | Notes |
|-|-|-|-|
| `Domain` | `EncryptableText` | `"domain"` | The [Domain][Domain Property] used in authentication. |
| `Username` | `EncryptableText` | `"username"` | The [Username][Username Property] used in authentication. |
| `Password` | `EncryptedText` | `"encryptedPassword"` | The [Password][Password Property] used in authentication. This property is an [EncryptedText][] and so it must be encrypted, for more information on how to encrypt the password, see [EncryptedText][].  |

### Convert UserCredentials to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)UserCredentials.ToString()` | `"Cortex.DataTypes.Credentials.UserCredentials"` | Expression | ToString will return the Full Name of the UserCredentials Data Type |
| Use `Convert Object To Text` block | where `Object` property has a value of `{"Domain": "domain", "Username": "username", "Password": "encryptedPassword"}` | `"Cortex.DataTypes.Credentials.UserCredentials"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `{"Domain": "domain", "Username": "username", "Password": "encryptedPassword"}` | `"{\r\n  \"Domain\": \"domain\",\r\n  \"Username\": \"username\",\r\n  \"Password\": \"encryptedPassword\"\r\n}"` | N/A  | See [Convert Object To Json][] |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `UserCredentials`.
* The Literal Editor is available for [Input][] properties where the data type is `UserCredentials`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `UserCredentials`.

### Known Limitations

Currently, if the `ToString()` method is used on a UserCredentials, then its Full Name will be returned; instead of a representation of the data within the UserCredentials.

In future this limitation may be removed.

## See Also

### Related Data Types

* [BasicEmailSessionDetails][]
* [EncryptableText][]
* [EncryptedText][]

[Domain Property]: {{< ref "#domain" >}}
[Username Property]: {{< ref "#username" >}}
[Password Property]: {{< ref "#password" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}

[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}

[EncryptableText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptableText.MainDoc" >}}
[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

[UnencryptedTextException]: {{< url "Cortex.Reference.Exceptions.Common.UnencryptedTextException.MainDoc" >}}

[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
