---
title: "EmailSessionException"
linkTitle: "EmailSessionException"
description: "The exception thrown when an issue occurs while working with an email block."
---

# {{% param title %}}

<p class="namespace">(Cortex.Exceptions.Email.EmailSessionException)</p>

## Description

The exception thrown when an issue occurs while working with an email block.

There are multiple reasons that this exception can be thrown:

* [Invalid Port Provided][InvalidPortProvided]
* [Invalid Host Provided][InvalidHostProvided]
* [SSL-Wrapped Connection Required][SslWrappedConnectionRequired]
* [SSL-Wrapped Connection Not Supported][SslWrappedConnectionNotSupported]
* [Invalid Username or Password][InvalidUsernameOrPassword]
* [Invalid SSL Certificate][InvalidSslCertificate]
* [Invalid Client Credentials][InvalidClientCredentials]

## Reasons

### Invalid Port Provided

A [Category][] of `Socket` and an [Error Code][] of `100` indicates that the port provided is invalid.

#### Message Format

The format of the [Message][] is as follows:

```json
"The connection attempt to 'Host' ('<host>') on 'Port' (<port>) failed. The 'Server Details' in
'Email Session Details' has been provided a port that does not exist or the connection timed out.
Please click the HelpLink for more information on how to fix this."
```

#### How to Fix

Provide a valid port and ensure that the mail server is up and running without issues.

***

### Invalid Host Provided

A [Category][] of `Socket` and an [Error Code][] of `101` indicates the host provided is invalid.

#### Message Format

```json
"Invalid 'Host' ('<host>') provided. The 'Server Details' in 'Email Session Details' has been
provided a host that does not exist. Please click the HelpLink for more information on how to fix this."
```

#### How to Fix

Provide a valid host.

***

### SSL-Wrapped Connection Required

A [Category][] of `SSL` and an [Error Code][] of `200` indicates that an SSL-wrapped connection is required.

#### Message Format

```json
"The connection could not be established or disconnected unexpectedly. Check if the 'Port' (<port>) provided
requires that'Use SSL' be set to true. Please click the HelpLink for more information on how to fix this."
```

#### How to Fix

Change `UseSsl` in the [ServerDetails][] to `true`, or make a connection on a port which does not require an SSL-wrapped connection to be made.

***

### SSL-Wrapped Connection Not Supported

A [Category][] of `SSL` and an [Error Code][] of `201` indicates that one of the following issues occurred:

* An SSL-wrapped connection is not supported
* Certificate on the host is expired, untrusted or invalid
* Certificate replaced by anti-virus software in order to scan web traffic resulting in failed certificate validation
* CRL server is down

#### Message Format

```json
"The connection could not be established or disconnected unexpectedly. Check if the 'Port' (<port>)
provided requires that 'Use SSL' be set to false. If this is not the case, check the inner exception.
Please click the HelpLink for more information on how to fix this."
```

#### How to Fix

Change `UseSsl` in the [ServerDetails][] to `false`, or make a connection on a port which supports/requires an SSL-wrapped connection.

If the above suggestion does not fix the problem check if the anti-virus software on the server running the flow is replacing the SSL certificate in order to scan the web traffic and change the settings appropriately if needed.

If the issue persists, please check the inner exception as instructed by the [Message][].

***

### Invalid Username or Password

A [Category][] of `UserCredentials` and an [Error Code][] of `300` indicates that the username or password provided is incorrect.

#### Message Format

```json
"The provided 'Username' and 'Password' is incorrect. The 'User Credentials' in 'Email Session Details' has been provided
an incorrect username and password combination. Please click the HelpLink for more information on how to fix this."
```

#### How to Fix

Provide a valid username and password combination in the [UserCredentials][].

***

### Invalid SSL Certificate

A [Category][] of `OAuthCredentials` and an [Error Code][] of `400` indicates that an invalid certificate path or password has been provided.

#### Message Format

```json
"The 'Certificate Path' ('<certificate-path>') or 'Certificate Password' is invalid.The 'Gmail OAuth Certificate Credentials'
in 'Email Session Details' has been provided an incorrect certificate path or certificate password. Please click the HelpLink
for more information on how to fix this."
```

#### How to Fix

Provide a path pointing to a valid SSL certificate and ensure that the certificate password is correct.

***

### Invalid Client Credentials

A [Category][] of `OAuthCredentials` and an [Error Code][] of `401` indicates that an invalid client credentials have been provided.

#### Message Format

```json
"The 'From Address' ('<from-address>}') or 'Client Id' ('<client-id>') is invalid. The 'Gmail OAuth Certificate Credentials'
in 'Email Session Details' has been provided an incorrect email address or Client ID. Please click the HelpLink for more
information on how to fix this."
```

#### How to Fix

Provide a valid From Address and ensure that the Client ID is correct.

***

## Properties

### Exception Type

The type of the exception (i.e. `EmailSessionException`)

| | |
|-----------|------------|
| Data Type | [String][] |

### Message

The exception message, providing information about the exception that occurred.

| | |
|-----------|------------|
| Data Type | [String][] |

### Category

The category of the exception, which is used to categorise an exception if there are multiple reasons that the exception can occur.

For `EmailSessionException` there are the following categories:

* `Socket`
* `SSL`
* `UserCredentials`
* `OAuthCredentials`

| | |
|-----------|------------|
| Data Type | [String][] |

### Error Code

The error code for the exception, which is used to indicate the reason that the exception occurred, if there are multiple reasons that the exception can occur.

For `EmailSessionException` there are the following error codes:

* [100][InvalidPortProvided] - indicates that the port provided is invalid
* [101][InvalidHostProvided] - indicates that the host provided is invalid
* [200][SslWrappedConnectionRequired] - indicates that an SSL-wrapped connection is required
* [201][SslWrappedConnectionNotSupported] - indicates that an SSL-wrapped connection is not supported
* [300][InvalidUsernameOrPassword] - indicated that the username and password combination is invalid
* [400][InvalidSslCertificate] - indicates that the certificate path or password provided is invalid
* [401][InvalidClientCredentials] - indicates that the from address or client ID provided is invalid

| | |
|-----------|---------------------------|
| Data Type | [EmailSessionErrorCode][] |

### Help Link

The URL for the relevant section of this exception's help page.

| | |
|-----------|------------|
| Data Type | [String][] |

## Remarks

### Known Limitations

None

## See Also

### Related Data Types

* [EmailSessionErrorCode][]
* [BasicEmailSessionDetails][]
* [ServerDetails][]
* [UserCredentials][]

### Related Concepts

* [Exceptions][]

### Related Blocks

* [Send Email Using SMTP Server Block][]
* [Send Email Using Gmail Block][]
* [Send Email Using Microsoft 365 Block][]

### External Documentation

None

[InvalidPortProvided]: {{< ref "#invalid-port-provided">}}
[InvalidHostProvided]: {{< ref "#invalid-host-provided">}}
[SslWrappedConnectionRequired]: {{< ref "#ssl-wrapped-connection-required">}}
[SslWrappedConnectionNotSupported]: {{< ref "#ssl-wrapped-connection-not-supported">}}
[InvalidSslCertificate]: {{< ref "#invalid-ssl-certificate">}}
[InvalidUsernameOrPassword]: {{< ref "#invalid-username-or-password">}}
[InvalidClientCredentials]: {{< ref "#invalid-client-credentials">}}

[Message]: {{< ref "#message" >}}
[Category]: {{< ref "#category" >}}
[Error Code]: {{< ref "#error-code" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[ServerDetails]: {{< url "Cortex.Reference.DataTypes.SessionDetails.ServerDetails.MainDoc" >}}
[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[BasicEmailSessionDetails]: {{< url "Cortex.Reference.DataTypes.Email.BasicEmailSessionDetails.MainDoc" >}}
[Exceptions]: {{< url "Cortex.Reference.Concepts.Fundamentals.Exceptions.MainDoc" >}}
[Send Email Using SMTP Server Block]: {{< url "Cortex.Reference.Blocks.Email.SendEmail.SendEmailUsingSmtpServer.MainDoc" >}}
[Send Email Using Gmail Block]: {{< url "Cortex.Reference.Blocks.GoogleWorkspace.Gmail.SendEmail.SendEmailUsingGmail.MainDoc" >}}
[Send Email Using Microsoft 365 Block]: {{< url "Cortex.Reference.Blocks.Microsoft365.Outlook.SendEmail.SendEmailUsingMicrosoft365.MainDoc" >}}
