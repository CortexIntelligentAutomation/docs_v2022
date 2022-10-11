---
title: "EmailSessionErrorCode"
linkTitle: "EmailSessionErrorCode"
description: "Used to represent an error code explaining the reason an `EmailSessionException` occurred."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Email.EmailSessionErrorCode)</p>

## Summary

The `EmailSessionErrorCode` data type is used to represent an error code explaining the reason an `EmailSessionException` occurred. For more information on the exception itself, see [EmailSessionException][].

| | |
|-|-|
| **Category:**          | Email                                                  |
| **Name:**              | `EmailSessionErrorCode`                                |
| **Full Name:**         | `Cortex.DataTypes.Email.EmailSessionErrorCode`         |
| **Alias:**             | N/A                                                    |
| **Description:**       | The data type used to represent an error code explaining the reason an `EmailSessionException` occurred. |
| **Default Value:**     | `0`                                                    |
| **Can be used as:**    | `EmailSessionErrorCode`, `Object`, `dynamic`           |
| **Can be cast to:**    | N/A                                                    |

## Values

### InvalidPort

| | |
|-|-|
| **Name:**    | InvalidPort                                     |
| **Value:**   | [Int32][] with value `100`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to an invalid port being provided in [ServerDetails][]. |

### InvalidHost

| | |
|-|-|
| **Name:**    | InvalidHost                                     |
| **Value:**   | [Int32][] with value `101`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to an invalid host being provided in [ServerDetails][]. |

### SslRequired

| | |
|-|-|
| **Name:**    | SslRequired                                     |
| **Value:**   | [Int32][] with value `200`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to `UseSsl` being set to `false` in [ServerDetails][] when trying to establish a connection on a host's port which requires SSL. |

### SslUnsupported

| | |
|-|-|
| **Name:**    | SslUnsupported                                  |
| **Value:**   | [Int32][] with value `201`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to `UseSsl` being set to `true` in [ServerDetails][] when trying to establish a connection on a host's port which does not support SSL. |

### InvalidUserCredentials

| | |
|-|-|
| **Name:**    | InvalidUserCredentials                          |
| **Value:**   | [Int32][] with value `300`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to an invalid username and password combination being provided in [UserCredentials][]. |

### InvalidCertificate

| | |
|-|-|
| **Name:**    | InvalidCertificate                              |
| **Value:**   | [Int32][] with value `400`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to an invalid certificate path and password combination being provided in [GmailOAuthCertificateCredentials][]. |

### InvalidGmailClientCredentials

| | |
|-|-|
| **Name:**    | InvalidGmailClientCredentials                   |
| **Value:**   | [Int32][] with value `401`                      |
| **Notes:**   | Used when an `EmailSessionException` occured due to an invalid `FromAddress` and `ClientId` combination being provided in [GmailOAuthCertificateCredentials][]. |

## Remarks

### Create an EmailSessionErrorCode

The following table shows some of the ways that `EmailSessionErrorCode` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use an enum expression | `EmailSessionErrorCode.InvalidPort` | `EmailSessionErrorCode.InvalidPort`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.InvalidHost` | `EmailSessionErrorCode.InvalidHost`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.SslRequired` | `EmailSessionErrorCode.SslRequired`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.SslUnsupported` | `EmailSessionErrorCode.SslUnsupported`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.InvalidUserCredentials` | `EmailSessionErrorCode.InvalidUserCredentials`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.InvalidCertificate` | `EmailSessionErrorCode.InvalidCertificate`| Expression | N/A |
| Use an enum expression | `EmailSessionErrorCode.InvalidGmailClientCredentials` | `EmailSessionErrorCode.InvalidGmailClientCredentials`| Expression | N/A |

An `EmailSessionErrorCode` can also be created using the Literal Editor by selecting the desired option from the dropdown list containing the range of options.

### Convert EmailSessionErrorCode to Text

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString` | `($)EmailSessionErrorCode.ToString()` where `($)EmailSessionErrorCode` has a value of `EmailSessionErrorCode.InvalidPort`| `"InvalidPort"` | Expression | ToString will return the Name of the enum value |
| Use `Convert Object To Text` block | where `Object` property has a value of `EmailSessionErrorCode.InvalidPort` | `"InvalidPort"` | N/A  | See [Convert Object To Text][] |
| Use `Convert Object To Json` block | where `Object` property has a value of `EmailSessionErrorCode.InvalidPort` | `"100"` | N/A  | See [Convert Object To Json][] |

### Casting an Int32 to EmailSessionErrorCode

[Int32][] values can be cast to an `EmailSessionErrorCode` in the following ways:

| Example | Result | Editor&nbsp;Support |
|-|-|-|
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `100` | `EmailSessionErrorCode.InvalidPort` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `101` | `EmailSessionErrorCode.InvalidHost` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `200` | `EmailSessionErrorCode.SslRequired` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `201` | `EmailSessionErrorCode.SslUnsupported` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `300` | `EmailSessionErrorCode.InvalidUserCredentials` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `400` | `EmailSessionErrorCode.InvalidCertificate` | Expression |
| `(EmailSessionErrorCode)($)IntVar` where `($)IntVar` has a value `401` | `EmailSessionErrorCode.InvalidGmailClientCredentials` | Expression |

For more information on casting [Int32][] values to enums, see [Working with Enums][].

### Property Editor Support

* The Expression Editor is available for [Input][] properties where the data type is `EmailSessionErrorCode`.
* The Literal Editor is available for [Input][] properties where the data type is `EmailSessionErrorCode`.
* The Variable Editor is available for [InputOutput][] and [Output][] properties where the data type is `EmailSessionErrorCode`.

### Known Limitations

Currently for the [SslUnsupported][] error code, there are numerous reasons for why the exception may have occurred. For more information, see [SSL Not Supported][].

In the future this may change.

## See Also

### Related Data Types

* [EmailSessionException][]

### Related Concepts

* [Working with Enums][]

### External Documentation

None

[SslUnsupported]: {{< ref "#sslunsupported">}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}

[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[EmailSessionException]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.MainDoc" >}}
[GmailOAuthCertificateCredentials]: {{< url "Cortex.Reference.DataTypes.GoogleWorkspace.Gmail.Authentication.OAuth.GmailOAuthCertificateCredentials.MainDoc" >}}
[SSL Not Supported]: {{< url "Cortex.Reference.Exceptions.Email.EmailSessionException.SslUnsupported" >}}

[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}
[Working with Enums]: {{< url "Cortex.Reference.Concepts.WorkingWith.Enums.MainDoc" >}}
[Convert Object To Text]: {{< url "Cortex.Reference.Blocks.Objects.ConvertObject.ConvertObjectToText.MainDoc" >}}
[Convert Object To Json]: {{< url "Cortex.Reference.Blocks.Json.ConvertJson.ConvertObjectToJson.MainDoc" >}}
