---
title: "UserCredentials"
linkTitle: "UserCredentials"
description: "Used for authentication."
---


# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Credentials.UserCredentials)</p>

## Summary

The `UserCredentials` data type is used for authentication.

| | |
|-|-|
| **Category:**          | Credentials                                            |
| **Name:**              | `UserCredentials`                                      |
| **Full Name:**         | `Cortex.DataTypes.Credentials.UserCredentials`         |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type used for authentication.                 |
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

The Password is used to define the password to be used in authentication.

| | |
|--------------------|---------------------------|
| Data Type | [EncryptedText][] |
| Is Advanced | `false` |
| Default Editor | [Expression][] |
| Default Value | [EncryptedText][] with value `""` |

## Remarks

### Create a UserCredentials

The following table shows some of the ways that `UserCredentials` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `UserCredentials` constructor | `new UserCredentials("domain", "username", "encryptedPassword")` | `{"Domain": "domain", "Username": "username", "Password": "encryptedPassword"}` | Expression |  |
| Use a `UserCredentials` constructor | `new UserCredentials("username", "encryptedPassword")` | `{"Domain": null, "Username": "username", "Password": "encryptedPassword"}` | Expression |  |

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `UserCredentials`.
* The Literal Editor is available for [Input][] properties where the data type is `UserCredentials`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `UserCredentials`.
  
### Known Limitations

None

## See Also

### Related Data Types

* [BasicEmailSessionDetails][]
* [EncryptableText][]
* [EncryptedText][]

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}

[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}

[EncryptableText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptableText.MainDoc" >}}
[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}
