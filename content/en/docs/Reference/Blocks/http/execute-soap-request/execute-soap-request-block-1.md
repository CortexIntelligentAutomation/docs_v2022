---
title: "Execute Soap Request"
linkTitle: "Execute Soap Request"
description: "Executes a SOAP request and returns a response."
---

{{< figure src="/blocks/http-execute-soap-request-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Http.ExecuteSoapRequest.ExecuteSoapRequestBlock`1)</p>

{{% alert type="information" title="Information" %}}Improvements to this page are planned for the future; this will include further examples and remarks.{{% /alert %}}

## Description

Executes a [Soap Request][Soap Request Property] using the specified [Http Credentials][Http Credentials Property] and returns the [Soap Response][Soap Response Property].

## Examples

### Executing a request with no authentication

***

### Executing a request using Basic authentication

***

### Executing a request using OAuth password credentials

***

### Executing a request using OAuth client credentials

***

## Properties

### Soap Request

The [Soap Request][Soap Request Property] to execute using the [Http Credentials][Http Credentials Property]. This property contains all of the information in relation to the request to be sent, these are:

- [SoapMessage][SoapMessage Property]
- [Uri][]
- [Headers][Headers Request]
- [HttpVersion][]

For more detailed information on each of the properties, see [SoapRequest][].

|||
|----------|----------|
| Data Type | [SoapRequest][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | [SoapRequest][] with value shown below: |

```json
{
    "SoapMessage": {
        "Action": "",
        "Envelope": "",
        "Version": 11
    },
    "Uri": "",
    "Headers": null,
    "HttpVersion": "HttpRequestVersion.HTTP10"
}
```

### Http Credentials

The [Http Credentials][Http Credentials Property] object that includes all of the information required for authentication. Mutliple authentication mechanisms are supported which correspond to specific values/data types:

- `null`: No authentication
- [UserCredentials][]: Basic authentication
- [HttpOAuthPasswordCredentials][]: OAuth authentication using password credentials
- [HttpOAuthClientCredentials][]: OAuth authentication using client credentials

Note that when using [HttpOAuthPasswordCredentials][] or [HttpOAuthClientCredentials][] as the [Http Credentials][Http Credentials Property], the Execute Soap Request block automatically handles retrieval of access tokens using the following rules:

- If an access token does not exist, a new access token will be retrieved and used when executing the [Soap Request][Soap Request Property].
- If an access token already exists but is expired, a new access token will be retrieved and used when executing the [Soap Request][Soap Request Property].
- If an access token already exists and is valid, it will be used when executing the [Soap Request][Soap Request Property].

|||
|----------|----------|
| Data Type | [HttpCredentials][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)HttpCredentials` with no value |

### Soap Response

The [Soap Response][Soap Response Property] object which contains the response returned from the server. This property contains all of the information in relation to the response from the server, these are:

- [ResponseEnvelope][]
- [ErrorMessage][]
- [Headers][Headers Response]
- [StatusCode][]

Note that if the [Headers][Headers Response] contains a key of `Content-Type` with a value containing `json` or `xml`, the [ResponseEnvelope][] will be set to a [Structure][] containing the data.

For more detailed information on each of the properties, see [SoapResponse][].

|||
|----------|----------|
| Data Type | [SoapResponse][] |
| Property Type | [Output][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)SoapResponse` with no value |

## Exceptions

The exceptions thrown by the block can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| [HttpAuthorisationException][] | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [ResourceOwnerUsername][ResourceOwnerUsername Password Credentials] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [ResourceOwnerPassword][ResourceOwnerPassword Password Credentials] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is invalid. |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is invalid. |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is invalid. |
| [InvalidRequestException][] | Thrown when the [Uri][] within [Soap Request][Soap Request Property] is not in the correct format or contains invalid characters. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is not in the correct format or contains invalid characters. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is not in the correct format or contains invalid characters. |
| | Thrown when a header key in [Headers][Headers Request] within [Soap Request][Soap Request Property] is empty (i.e. `""`). |
| | Thrown when a header key in [Headers][Headers Request] within [Soap Request][Soap Request Property] is restricted. |
| | Thrown when a header key in [Headers][Headers Request] within [Soap Request][Soap Request Property] is restricted and forbidden. |
| | Thrown when a header value in [Headers][Headers Request] within [Soap Request][Soap Request Property] could not be assigned to its restricted header key. |
| | Thrown when a header value in [Headers][Headers Request] within [Soap Request][Soap Request Property] could not be converted to its restricted header key's type. |
| | Thrown when the [Envelope][] in the [SoapMessage][SoapMessage Property] within [Soap Request][Soap Request Property] is not valid XML. |
| | Thrown when the [HttpVersion][] within [Soap Request][Soap Request Property] is not one of the specified [HttpRequestVersion][] values (e.g. `(HttpRequestVersion)20`). |
| [InvalidResponseException][] | Thrown when the [ResponseEnvelope][] within [Soap Response][Soap Response Property] is not valid XML. |
| [PropertyNullException][] | Thrown when the [Soap Request][Soap Request Property] is `null`. |
| | Thrown when the [Uri][] within [Soap Request][Soap Request Property] is `null`. |
| | Thrown when the [SoapMessage][SoapMessage Property] within [Soap Request][Soap Request Property] is `null`. |
| | Thrown when the [Action][] in the [Soap11Message][] within [Soap Request][Soap Request Property] is `null`. |
| | Thrown when the [Envelope][] in the [SoapMessage][SoapMessage Property] within [Soap Request][Soap Request Property] is `null`. |
| | Thrown when the [Username][] within [UserCredentials][] is `null`. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is `null`. |
| | Thrown when the [ResourceOwnerUsername][ResourceOwnerUsername Password Credentials] within [HttpOAuthPasswordCredentials][] is `null`. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientAuthentication][ClientAuthentication Client Credentials] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is `null`. |
| [PropertyEmptyException][] | Thrown when the [Uri][] within [Soap Request][Soap Request Property] is empty (i.e. `""`). |
| | Thrown when the [Username][] within [UserCredentials][] is empty (i.e. `""`). |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ResourceOwnerUsername][ResourceOwnerUsername Password Credentials] within [HttpOAuthPasswordCredentials][] is empty (i.e. `""`). |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |

## Remarks

### Known Limitations

None

[Soap Request Property]: {{< ref "#soap-request" >}}
[Http Credentials Property]: {{< ref "#http-credentials" >}}
[Soap Response Property]: {{< ref "#soap-response" >}}

[SoapRequest]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.MainDoc" >}}
[SoapMessage Property]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.SoapMessage" >}}
[Uri]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.Uri" >}}
[Headers Request]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.Headers" >}}
[HttpVersion]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.HttpVersion" >}}

[SoapMessage]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapMessage.MainDoc" >}}
[Envelope]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapMessage.Envelope" >}}

[Soap11Message]: {{< url "Cortex.Reference.DataTypes.Http.Soap.Soap11Message.MainDoc" >}}
[Action]: {{< url "Cortex.Reference.DataTypes.Http.Soap.Soap11Message.Action" >}}

[Soap12Message]: {{< url "Cortex.Reference.DataTypes.Http.Soap.Soap12Message.MainDoc" >}}

[HttpCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.HttpCredentials.MainDoc" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[Username]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Username" >}}
[Password]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Password" >}}

[HttpOAuthClientCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.MainDoc" >}}
[AccessTokenUri Client Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.AccessTokenUri" >}}
[ClientAuthentication Client Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.ClientAuthentication" >}}

[HttpOAuthPasswordCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.MainDoc" >}}
[ResourceOwnerUsername Password Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.ResourceOwnerUsername" >}}
[ResourceOwnerPassword Password Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.ResourceOwnerPassword" >}}
[AccessTokenUri Password Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.AccessTokenUri" >}}

[ClientAuthentication]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.MainDoc" >}}
[ClientId]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.ClientId" >}}
[ClientSecret]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.ClientSecret" >}}
[SendAs]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.SendAs" >}}

[SoapResponse]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapResponse.MainDoc" >}}
[ResponseEnvelope]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapResponse.ResponseEnvelope" >}}
[ErrorMessage]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapResponse.ErrorMessage" >}}
[Headers Response]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapResponse.Headers" >}}
[StatusCode]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapResponse.StatusCode" >}}

[HttpRequestVersion]: {{< url "Cortex.Reference.DataTypes.Http.HttpRequestVersion.MainDoc" >}}
[HTTP10]: {{< url "Cortex.Reference.DataTypes.Http.HttpRequestVersion.HTTP10" >}}
[HTTP11]: {{< url "Cortex.Reference.DataTypes.Http.HttpRequestVersion.HTTP11" >}}

[Structure]: {{< url "Cortex.Reference.DataTypes.Collections.Structure.MainDoc" >}}

[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}
[HttpAuthorisationException]: {{< url "Cortex.Reference.Exceptions.Http.HttpAuthorisationException.MainDoc" >}}
[InvalidRequestException]: {{< url "Cortex.Reference.Exceptions.Http.InvalidRequestException.MainDoc" >}}
[InvalidResponseException]: {{< url "Cortex.Reference.Exceptions.Http.InvalidResponseException.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}

[API]: {{< url "Cortex.Reference.Glossary.A-E.API" >}}
