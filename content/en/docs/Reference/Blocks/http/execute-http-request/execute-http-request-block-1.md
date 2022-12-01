---
title: "Execute Http Request"
linkTitle: "Execute Http Request"
description: "Executes an HTTP request and returns a response."
---

{{< figure src="/blocks/http-execute-http-request-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Http.ExecuteHttpRequest.ExecuteHttpRequestBlock`1)</p>

{{% alert type="information" title="Information" %}}Improvements to this page are planned for the future; this will include further examples and remarks.{{% /alert %}}

## Description

Executes an [HTTP request][Http Request Property] using the specified [Http Credentials][Http Credentials Property] and returns the [Http Response][Http Response Property].

## Examples

### Executing a GET request

### Executing a POST request

### Executing a request using Basic authentication

### Executing a request using OAuth password credentials

### Executing a request using OAuth client Credentials

## Properties

### Http Request

The [Http Request][Http Request Property] to execute using the [Http Credentials][Http Credentials Property]. This property contains all of the information in relation to the request to be sent, these are:

- [Uri][]
- [QueryParameters][]
- [Verb][]
- [ContentType][]
- [Headers][]
- [Body][]
- [HttpVersion][]

For more detailed information on each of the properties, see [HttpRequest][].

|||
|----------|----------|
| Data Type | [HttpRequest][] |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | [HttpRequest][] with value shown below: |

```json
{
    "Uri": "",
    "QueryParameters": null,
    "Verb": "RequestVerb.GET",
    "ContentType": "application/json",
    "Headers": null,
    "Body": "",
    "HttpVersion": "HttpRequestVersion.Http10"
}
```

### Http Credentials

The [Http Credentials][Http Credentials Property] object that includes all of the information required for authentication. Mutliple authentication mechanisms are supported which correspond to specific values/data types:

- `null`: No authentication
- [UserCredentials][]: Basic authentication
- [HttpOAuthPasswordCredentials][]: OAuth authentication using password credentials
- [HttpOAuthClientCredentials][]: OAuth authentication using client credentials

|||
|----------|----------|
| Data Type | [HttpCredentials][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | `($)HttpCredentials` with no value |

### Http Response

The [Http Response][Http Response Property] object which contains the response returned from the server. This property contains all of the information in relation to the response from the server, these are:

- [ResponseBody][]
- [ErrorMessage][]
- [Headers][]
- [StatusCode][]

For more detailed information on each of the properties, see [HttpResponse][].

|||
|----------|----------|
| Data Type | [HttpResponse][] |
| Property Type | [Output][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)HttpResponse` with no value |

## Exceptions

The exceptions thrown by the block can be found below:

| Name                                 | Description |
|--------------------------------------|-------------|
| [HttpAuthorisationException][] | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [ResourceOwnerUsername][] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [ResourceOwnerPassword][] within [HttpOAuthPasswordCredentials][] is invalid. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is invalid. |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is invalid. |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is invalid. |
| [InvalidRequestException][] | Thrown when the [Uri][] within [Http Request][Http Request Property] is not in the correct format or contains invalid characters. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is not in the correct format or contains invalid characters. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is not in the correct format or contains invalid characters. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is not in the correct format or contains invalid characters. |
| [PropertyNullException][] | Thrown when the [Http Request][Http Request Property] is `null`. |
| | Thrown when the [Username][] within [UserCredentials][] is `null`. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is `null`. |
| | Thrown when the [ResourceOwnerUsername][] within [HttpOAuthPasswordCredentials][] is `null`. |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientAuthentication][ClientAuthentication Client Credentials] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is `null`. |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is `null`. |
| [PropertyEmptyException][] | Thrown when the [Uri][] within [Http Request][Http Request Property] is empty (i.e. `""`). |
| | Thrown when the [Username][] within [UserCredentials][] is empty (i.e. `""`). |
| | Thrown when the [AccessTokenUri][AccessTokenUri Password Credentials] within [HttpOAuthPasswordCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ResourceOwnerUsername][] within [HttpOAuthPasswordCredentials][] is empty (i.e. `""`). |
| | Thrown when the [AccessTokenUri][AccessTokenUri Client Credentials] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ClientId][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |
| | Thrown when the [ClientSecret][] in [ClientAuthentication][] within [HttpOAuthClientCredentials][] is empty (i.e. `""`). |

## Remarks

### Known Limitations

None

[Http Request Property]: {{< ref "#http-request" >}}
[Http Credentials Property]: {{< ref "#http-credentials" >}}
[Http Response Property]: {{< ref "#http-response" >}}

[UserCredentials]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.MainDoc" >}}
[Username]: {{< url "Cortex.Reference.DataTypes.Credentials.UserCredentials.Username" >}}

[HttpCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.HttpCredentials.MainDoc" >}}

[HttpOAuthClientCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.MainDoc" >}}
[ResourceOwnerUsername]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.ResourceOwnerUsername" >}}
[ResourceOwnerPassword]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.ResourceOwnerPassword" >}}
[AccessTokenUri Client Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.AccessTokenUri" >}}
[ClientAuthentication Client Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthClientCredentials.ClientAuthentication" >}}

[HttpOAuthPasswordCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.MainDoc" >}}
[AccessTokenUri Password Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.AccessTokenUri" >}}
[AccessTokenUri Password Credentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.HttpOAuthPasswordCredentials.AccessTokenUri" >}}

[HttpCredentials]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.HttpCredentials.MainDoc" >}}

[ClientAuthentication]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.MainDoc" >}}
[ClientId]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.ClientId" >}}
[ClientSecret]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.ClientSecret" >}}
[SendAs]: {{< url "Cortex.Reference.DataTypes.Http.Authentication.OAuth.ClientAuthentication.SendAs" >}}

[HttpRequest]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.MainDoc" >}}
[Uri]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.Uri" >}}
[QueryParameters]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.QueryParameters" >}}
[Verb]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.Verb" >}}
[ContentType]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.ContentType" >}}
[Headers]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.Headers" >}}
[Body]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.Body" >}}
[HttpVersion]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpRequest.HttpVersion" >}}

[HttpResponse]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpResponse.MainDoc" >}}
[ResponseBody]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpResponse.ResponseBody" >}}
[ErrorMessage]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpResponse.ErrorMessage" >}}
[Headers]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpResponse.Headers" >}}
[StatusCode]: {{< url "Cortex.Reference.DataTypes.Http.Rest.HttpResponse.StatusCode" >}}

[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}
[HttpAuthorisationException]: {{< url "Cortex.Reference.Exceptions.Http.HttpAuthorisationException.MainDoc" >}}
[InvalidRequestException]: {{< url "Cortex.Reference.Exceptions.Http.InvalidRequestException.MainDoc" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
