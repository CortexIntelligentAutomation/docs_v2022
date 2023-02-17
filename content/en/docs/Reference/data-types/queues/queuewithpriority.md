---
title: "QueueWithPriority"
linkTitle: "QueueWithPriority"
description: "A data type that operates like a Priority Queue, but preserves FIFO between items of the same priority."
---

# {{% param title %}}

<p class="namespace">(DataTypes.Queues.QueueWithPriority`2)</p>

## Summary

A data type that operates like a [PriorityQueue][], but preserves first-in-first-out between items of the same priority.

When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, a priority value can be provided to prioritise some items over others when dequeuing.

| | |
|-|-|
| **Category:**          | Queues                                                        |
| **Name:**              | `QueueWithPriority<TItem, TPriority>`                                           |
| **Full Name:**         | `DataTypes.Queues.QueueWithPriority<TItem, TPriority>`                          |
| **Alias:**             | N/A                                                           |
| **Description:**       | A data type that operates like a [PriorityQueue][], but preserves first-in-first-out between items of the same priority. When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, a priority value can be provided to prioritise some items over others when dequeuing.|
| **Size:**              | Varies                                                        |
| **Default Value:**     | `null`                                                        |
| **Can be used as:**    | `Object`, `dynamic`                                           |
| **Can be cast to:**    | N/A                                                           |

## Properties

### UserComparer

The [IComparer][] used to compare [TPriority][] values.
  
| | |
|--------------------|---------------------------|
| Data Type | [IComparer][] |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)UserComparer` with no value. |

## Methods

The following table shows the methods included in `QueueWithPriority<TItem, TPriority>`.

| Method | Example | Result | Notes |
|-|-|-|-|
| `void Enqueue(TItem item, TPriority priority)` | `queue.Enqueue("Some Value", 0)` | `{"Items": [{Item: "Some Value", Priority: 0}], "UserComparer": {}}` |  |
| `TItem Dequeue()` | `queue.Dequeue()` | `"Some Value"` | `{Item: "Some Value", Priority: 0}` is removed from the queue. |
| `TItem Peek()` | `queue.Peek()` | `"Some Value"` | `{Item: "Some Value", Priority: 0}` remains in the queue. |

## Exceptions

The exceptions thrown by the block can be found below:

| Name     | Description |
|----------|----------|
| [ArgumentException][] | Thrown when [TPriority][] does not implement [IComparer][]. |
| [ArgumentNullException][] | Thrown when [UserComparer][UserComparer Property] is `null`. |

## Remarks

### Create a QueueWithPriority

The following table shows some of the ways that a `QueueWithPriority<TItem, TPriority>` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `QueueWithPriority<TItem, TPriority>` constructor | `new QueueWithPriority<string,int>()`                   | `{"Items": [], "UserComparer": {}}`            | Expression | Priority type must implement [IComparer][] as the [default][] type [Comparer][] is used to sort by priority. |
|                              | `new QueueWithPriority<string, object>(new ExampleObjectComparer())`                   | `{"Items": [], "UserComparer": Example.ObjectComparer}`            | Expression | A [Comparer][] for the priority type must be included. |

### Known Limitations

None

## See Also

### Related Data Types

None

### Related Concepts

None

### External Documentation

* [PriorityQueue][]
* [IComparer][]
* [Comparer][]

[UserComparer Property]: {{< ref "#usercomparer" >}}

[ArgumentException]: {{< url "MSDocs.DotNet.Api.System.ArgumentException" >}}
[ArgumentNullException]: {{< url "MSDocs.DotNet.Api.System.ArgumentNullException" >}}

[PriorityQueue]: {{< url "MSDocs.DotNet.Api.System.PriorityQueue.MainDoc" >}}
[IComparer]: {{< url "MSDocs.DotNet.Api.System.IComparer.MainDoc" >}}
[Comparer]: {{< url "MSDocs.DotNet.Api.System.Comparer.MainDoc" >}}
[default]: {{< url "MSDocs.DotNet.Api.System.Comparer.Default" >}}

[Variable]: {{< url "Cortex.Reference.Concepts.Fundamentals.Blocks.BlockProperties.PropertyEditors.VariableEditor.MainDoc" >}}
[TPriority]: {{< url "Cortex.Reference.Concepts.Fundamentals.DataTypes.Generics.MainDoc" >}}
