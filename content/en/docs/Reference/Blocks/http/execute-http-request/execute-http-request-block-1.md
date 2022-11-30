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

The [Http Request][Http Request Property] to execute using the [Http Credentials][Http Credentials Property].

For more detailed information on each of the properties see [HttpRequest][].

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

The [Http Credentials][Http Credentials Property] object that includes all of the information required for authentication.

|||
|----------|----------|
| Data Type | [HttpCredentials][] |
| Property Type | [InputOutput][] |
| Is [Advanced][] | `false` |
| Default Editor | [Literal][] |
| Default Value | `($)HttpCredentials` with no value |

### Http Response

The [Http Response][Http Response Property] object which contains the response returned from the server.

For more detailed information on each of the properties, see [HttpResponse][].

|||
|----------|----------|
| Data Type | [HttpResponse][] |
| Property Type | [Output][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)HttpResponse` with no value |

## Exceptions

## Remarks

### Known Limitations

None

[Http Request Property]: {{< ref "#http-request" >}}
[Http Credentials Property]: {{< ref "#http-credentials" >}}
[Http Response Property]: {{< ref "#http-response" >}}

[Expression]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.ExpressionEditor.MainDoc" >}}
[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Variables.UsingVariables.MainDoc" >}}
[Literal]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.LiteralEditor.MainDoc" >}}
[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[InputOutput]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.InputOutput" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}
