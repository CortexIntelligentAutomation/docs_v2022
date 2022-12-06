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

The following examples will use an example [API][] with a base [Uri][] of `https://test-shop.com/api` and resource called `items` at `https://test-shop.com/api/items`. Each example assumes that the resource `items` contains the following data before the example is executed:

```xml

```

The example [API][] supports:

- Retrieval of every item in the `items` resource via a [GET][] request which returns the `items` resource as the [ResponseEnvelope][] of the [Soap Response][Soap Response Property]
- Creation of a new item in the `items` resource via a [POST][] request which returns the updated `items` resource as the [ResponseEnvelope][] of the [Soap Response][Soap Response Property]
- Unauthenticated requests
- Basic authentication
- Retrieval of access tokens from `https://test-shop.com/api/oauth2/token`
- OAuth authentication using password credentials
- OAuth authentication using client credentials

## Properties

### Soap Request

The [Soap Request][Soap Request Property] to execute using the [Http Credentials][Http Credentials Property]. This property contains all of the information in relation to the request to be sent, these are:

- [SoapMessage][]
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
    "HttpVersion": "HttpRequestVersion.Http10"
}
```

### Http Credentials

The [Http Credentials][Http Credentials Property] object that includes all of the information required for authentication. Mutliple authentication mechanisms are supported which correspond to specific values/data types:

- `null`: No authentication
- [UserCredentials][]: Basic authentication
- [HttpOAuthPasswordCredentials][]: OAuth authentication using password credentials
- [HttpOAuthClientCredentials][]: OAuth authentication using client credentials

Note that when using [HttpOAuthPasswordCredentials][] or [HttpOAuthClientCredentials][] as the [Http Credentials][Http Credentials Property], the Execute Http Request block automatically handles retrieval of access tokens using the following rules:

- If an access token does not exist, a new access token will be retrieved and used when executing the [Soap Request][Soap Request Property].
- If an access token already exists but is expired, a new access token will be retrieved and used when executing the [Soap Request][Soap Request Property].
- If an access token already exists and is valid, it will be used when executing the [Soap Request][Soap Request Property].

|||
|----------|----------|
| Data Type | [HttpCredentials][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
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
| Default Editor | [Literal][] |
| Default Value | `($)SoapResponse` with no value |

## Exceptions

The exceptions thrown by the block can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| | |

## Remarks

### Known Limitations

None

[Soap Request Property]: {{< ref "#soap-request" >}}
[Http Credentials Property]: {{< ref "#http-credentials" >}}
[Soap Response Property]: {{< ref "#soap-response" >}}

[SoapRequest]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.MainDoc" >}}
[SoapMessage]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.SoapMessage" >}}
[Uri]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.Uri" >}}
[Headers Request]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.Headers" >}}
[HttpVersion]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.HttpVersion" >}}

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

[SoapResponse]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.MainDoc" >}}
[ResponseEnvelope]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.ResponseEnvelope" >}}
[ErrorMessage]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.ErrorMessage" >}}
[Headers Response]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.Headers" >}}
[StatusCode]: {{< url "Cortex.Reference.DataTypes.Http.Soap.SoapRequest.StatusCode" >}}

[RequestVerb]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.MainDoc" >}}
[GET]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.GET" >}}
[POST]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.POST" >}}
[PUT]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.PUT" >}}
[DELETE]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.DELETE" >}}
[PATCH]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.PATCH" >}}
[HEAD]: {{< url "Cortex.Reference.DataTypes.Http.RequestVerb.HEAD" >}}

[Structure]: {{< url "Cortex.Reference.DataTypes.Collections.Structure.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}

[API]: {{< url "Cortex.Reference.Glossary.A-E.API" >}}
