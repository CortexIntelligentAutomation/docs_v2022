---
title: "GmailOAuthCertificateCredentials"
linkTitle: "GmailOAuthCertificateCredentials"
description: "The data type representing configuration for authentication via OAuth when establishing a connection with a mail server hosted by Gmail."
weight: 1
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.GoogleWorkspace.Gmail.Authentication.OAuth.GmailOAuthCertificateCredentials)</p>

## Summary

The `GmailOAuthCertificateCredentials` data type is used to represent configuration for authentication via OAuth when establishing a connection with a mail server hosted by [Gmail][].

| | |
|-|-|
| **Category:**          | Email |
| **Name:**              | `GmailOAuthCertificateCredentials` |
| **Full Name:**         | `Cortex.DataTypes.GoogleWorkspace.Gmail.Authentication.OAuth.GmailOAuthCertificateCredentials` |
| **Alias:**             | N/A |
| **Description:**       | Configuration for authentication via OAuth when establishing a connection with a mail server hosted by [Gmail][]. |
| **Default Value:**     | null |
| **Can be used as:**    | `GmailOAuthCertificateCredentials`, `Object`, `dynamic` |
| **Can be cast to:**    | N/A |

## Properties

### CertificatePath

The CertificatePath is used to define

### CertificatePassword

The CertificatePassword is used to define

### FromAddress

The FromAddress is used to define

### ClientId

The ClientId is used to define

## Exceptions

The exceptions thrown by the data type can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| [UnencryptedTextException][]         |Thrown when the [CertificatePassword][CertificatePassword Property] is not encrypted. |

## Remarks

### Create a GmailOAuthCertificateCredentials

### Convert GmailOAuthCertificateCredentials to Text

### Property Editor Support

- The Expression Editor is available for [Input][] properties where the data type is `GmailOAuthCertificateCredentials`.
- The Literal Editor is available for [Input][] properties where the data type is `GmailOAuthCertificateCredentials`.
- The Variable Editor is available for [Input][], [InputOutput][] and [Output][] properties where the data type is `GmailOAuthCertificateCredentials`.

### Known Limitations

None

## See Also

### Related Data Types

- [GmailSessionDetails][]
- [EncryptedText][]

### Related Concepts

- [Working with Email][]

### External Documentation

None

[CertificatePassword Property]: {{< ref "#certificatepassword" >}}

[GmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.GoogleWorkspace.Gmail.GmailSessionDetails.MainDoc" >}}

[EncryptedText]: {{< url "Cortex.Reference.DataTypes.Text.EncryptedText.MainDoc" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}

[UnencryptedTextException]: {{< url "Cortex.Reference.Exceptions.Common.UnencryptedTextException.MainDoc" >}}

[Working with Email]: {{< url "Cortex.Reference.Concepts.WorkingWith.Email.MainDoc" >}}
[Setting up an app password for a Gmail account]: {{< url "Cortex.Reference.Concepts.WorkingWith.Email.Authentication.SettingUpAppPassword" >}}
[Setting up a Gmail account for OAuth authentication]: {{< url "Cortex.Reference.Concepts.WorkingWith.Email.Authentication.SettingUpOAuthGmail" >}}

[Gmail]: {{< url "Cortex.Reference.Glossary.F-J.Gmail" >}}
