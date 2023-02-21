---
title: "QueueWithPriority"
linkTitle: "QueueWithPriority"
description: "A data type that operates like a Priority Queue, but preserves first-in-first-out between items of the same priority."
---

# {{% param title %}}

<p class="namespace">(DataTypes.Queues.QueueWithPriority`2)</p>

## Summary

A data type that operates like a [PriorityQueue][], but preserves first-in-first-out between items of the same priority.

When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, [TPriority][] can be used to order items within the queue.

| | |
|-|-|
| **Category:**          | Queues                                                        |
| **Name:**              | `QueueWithPriority<TItem, TPriority>`                                           |
| **Full Name:**         | `DataTypes.Queues.QueueWithPriority<TItem, TPriority>`                          |
| **Alias:**             | N/A                                                           |
| **Description:**       | A data type that operates like a [PriorityQueue][], but preserves first-in-first-out between items of the same priority. When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, [TPriority][] can be used to order items within the queue.|
| **Size:**              | Varies                                                        |
| **Default Value:**     | `null`                                                        |
| **Can be used as:**    | `QueueWithPriority<TItem, TPriority>`, `Object`, `dynamic`                                           |
| **Can be cast to:**    | N/A                                                           |

## Properties

### PriorityComparer

The [IComparer][] used to compare [TPriority][] values.
  
| | |
|--------------------|---------------------------|
| Data Type | [IComparer][]&lt;[TPriority][]&gt; |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)PriorityComparer` with no value. |

## Methods

The following table shows the methods included in `QueueWithPriority<TItem, TPriority>`.

| Method | Initial Queue | Example | Result | Notes |
|-|-|-|-|-|
| `void Enqueue(TItem item, TPriority priority)` | `{"Items": [], "PriorityComparer": {}}` |`queue.Enqueue("Some Value", 0)` | `{"Items": [{Item: "Some Value", Priority: 0}], "PriorityComparer": {}}` | `{Item: "Some Value", Priority: 0}` is added to the queue. |
| `TItem Dequeue()` | `{"Items": [{Item: "Some Value", Priority: 0}], "PriorityComparer": {}}` | `queue.Dequeue()` | `"Some Value"` | `{Item: "Some Value", Priority: 0}` is removed from the queue. |
| `TItem Peek()` | `{"Items": [{Item: "Some Value", Priority: 0}], "PriorityComparer": {}}` | `queue.Peek()` | `"Some Value"` | `{Item: "Some Value", Priority: 0}` remains in the queue. |

## Exceptions

The exceptions thrown by the data type can be found below:

| Name     | Description |
|----------|----------|
| [ArgumentException][] | Thrown when [TPriority][] does not implement [IComparer][]. |
| [ArgumentNullException][] | Thrown when [PriorityComparer][PriorityComparer Property] is `null`. |

## Remarks

### Create a QueueWithPriority

The following table shows some of the ways that a `QueueWithPriority<TItem, TPriority>` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `QueueWithPriority<TItem, TPriority>` constructor | `new QueueWithPriority<string,int>()`                   | `{"Items": [], "PriorityComparer": {}}`            | Expression | Priority type must implement [IComparer][] because the [default][] type [Comparer][] is used to sort by priority. |
|                              | `new QueueWithPriority<string, object>(new ExampleObjectComparer())`                   | `{"Items": [], "PriorityComparer": Example.ObjectComparer}`            | Expression | A [Comparer][] for the [TPriority][] type must be included. |

### Known Limitations

None

## See Also

### Related Data Types

* [IComparer][]

### Related Concepts

None

### External Documentation

* [System.Collections.Generic.PriorityQueue&lt;TElement,TPriority>][PriorityQueue]
* [System.Collections.Generic.Comparer&lt;T>][Comparer]

[PriorityComparer Property]: {{< ref "#PriorityComparer" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}
[ArgumentNullException]: {{< url "MSDocs.DotNet.Api.System.ArgumentNullException" >}}

[PriorityQueue]: {{< url "MSDocs.DotNet.Api.System.PriorityQueue.MainDoc" >}}
[IComparer]: {{< url "Cortex.Reference.DataTypes.Collections.IComparer.MainDoc" >}}
[Comparer]: {{< url "MSDocs.DotNet.Api.System.Comparer.MainDoc" >}}
[default]: {{< url "MSDocs.DotNet.Api.System.Comparer.Default" >}}

[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}
[TPriority]: {{< url "Cortex.Reference.Concepts.Fundamentals.DataTypes.Generics.MainDoc" >}}

[Advanced]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.AdvancedProperties.MainDoc" >}}
