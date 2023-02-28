---
title: "Dequeue Item"
linkTitle: "Dequeue Item"
description: "Dequeues the item with the minimal priority from a queue."
---

{{< figure src="/blocks/queues-dequeue-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.Queues.DequeueItem.DequeueItemBlock)</p>

## Description

Dequeues the [Item][Item Property] with the minimal priority from the queue.

## Examples

### Dequeue from a Queue which contains items

This example will dequeue from [QueueWithPriority][]&lt;[String][], [Int32][]&gt; which contains `"Element -1"` with a priority of `-1` and `"Element 1"` with a priority of `1` and returns the element with the lowest priority.

#### Properties

| Property           | Value                     | Notes                                    |
|--------------------|---------------------------|------------------------------------------|
| [Queue][Queue Property] | `($)Queue`, with value `{"Items": [{"Item": "Element -1", "Priority": -1}, {"Item": "Element 1", "Priority": 1}], "PriorityComparer": {}}` is a variable of type [QueueWithPriority][]&lt;[String][], [Int32][]&gt; |
| [Item][Item Property] | `($)Item`, with no value | `($)Item` is a variable that will be set to type string |

#### Result

Dequeueing from the [Queue][Queue Property] results in the variable `($)Item` being updated to:

```json
"Element -1"
```

and `($)Queue` is updated to the value:

```json
{
    "Items": [
        {
            "Item": "Element 1", 
            "Priority": 1
        }
    ], 
    "PriorityComparer": {}
}
```

***

## Properties

### Queue

The [Queue][Queue Property] to peek from.
  
| | |
|--------------------|---------------------------|
| Data Type | [QueueWithPriority][]&lt;[TItem][], [TPriority][]&gt; |
| Property Type | [Input][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)Queue` with no value |

### Item

The [Item][Item Property] with minimal priority value.

| | |
|--------------------|---------------------------|
| Data Type | [TItem][] |
| Property Type | [Output][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)Item` with no value |

## Exceptions

The exceptions thrown by the block can be found below:

| Name     | Description |
|----------|----------|
| [PropertyNullException][] | Thrown when [Queue][Queue Property] is `null`. |
| [PropertyEmptyException][] | Thrown when [Queue][Queue Property] is `empty`.|

## Remarks

None

[Queue Property]: {{< ref "#queue" >}}
[Item Property]: {{< ref "#item" >}}

[Input]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Input" >}}
[Output]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.WhatIsABlockProperty.Output" >}}

[TItem]: {{< url "Cortex.Reference.Concepts.Fundamentals.DataTypes.Generics.MainDoc" >}}
[TPriority]: {{< url "Cortex.Reference.Concepts.Fundamentals.DataTypes.Generics.MainDoc" >}}

[QueueWithPriority]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyEmptyException.MainDoc" >}}

[PropertyNullException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}
[PropertyEmptyException]: {{< url "Cortex.Reference.Exceptions.Common.Property.PropertyNullException.MainDoc" >}}

[String]: {{< url "Cortex.Reference.DataTypes.Text.String.MainDoc" >}}
[Int32]: {{< url "Cortex.Reference.DataTypes.Numbers.Int32.MainDoc" >}}

[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
