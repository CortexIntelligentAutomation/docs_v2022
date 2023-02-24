---
title: "QueueWithPriority"
linkTitle: "QueueWithPriority"
description: "A data type that operates like a Priority Queue, but preserves first-in-first-out between items of the same priority."
---

# {{% param title %}}

<p class="namespace">(Cortex.DataTypes.Queues.QueueWithPriority`2)</p>

## Summary

The `QueueWithPriority<TItem, TPriority>` data type is used to represent a queue which orders items by priority (like a [PriorityQueue][]), but preserves first-in-first-out behaviour for items with the same priority.

When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, [TPriority][] is used to order items within the queue.

| | |
|-|-|
| **Category:**          | Queues                                                        |
| **Name:**              | `QueueWithPriority<TItem, TPriority>`                                           |
| **Full Name:**         | `Cortex.DataTypes.Queues.QueueWithPriority<TItem, TPriority>`                          |
| **Alias:**             | N/A                                                           |
| **Description:**       | A queue which orders items by priority (like a [PriorityQueue][]), but preserves first-in-first-out behaviour for items with the same priority. When enqueuing items into the `QueueWithPriority<TItem, TPriority>`, [TPriority][] is used to order items within the queue.|
| **Default Value:**     | `null`                                                        |
| **Can be used as:**    | `QueueWithPriority<TItem, TPriority>`, `Object`, `dynamic`                                           |
| **Can be cast to:**    | N/A                                                           |

## Properties

### PriorityComparer

The [IComparer][]&lt;[TPriority][]&gt; used to compare [TPriority][] values.
  
| | |
|--------------------|---------------------------|
| Data Type | [IComparer][]&lt;[TPriority][]&gt; |
| Is [Advanced][] | `false` |
| Default Editor | [Variable][] |
| Default Value | `($)PriorityComparer` with no value. |

## Exceptions

The exceptions thrown by the data type can be found below:

| Name     | Description |
|----------|----------|
| [ArgumentException][] | Thrown when [TPriority][] does not implement [IComparer][]&lt;[TPriority][]&gt;. |
| [ArgumentNullException][] | Thrown when [PriorityComparer][PriorityComparer Property] is `null`. |

## Remarks

### Create a QueueWithPriority

The following table shows some of the ways that a `QueueWithPriority<TItem, TPriority>` can be created.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use a `QueueWithPriority<TItem, TPriority>` constructor | `new QueueWithPriority<string,int>()`                   | `{"Items": [], "PriorityComparer": {}}`            | Expression | This constructor will try and use the default comparer defined for [TPriority][], only data types that implement [IComparer][]&lt;[TPriority][]&gt; have a default comparer. <br> <br> If [TPriority][] does not implement [IComparer][]&lt;[TPriority][]&gt; it will not have a default comparer and throw an [ArgumentException][], in this case you must used the constructor in the example below to provide a valid comparer. |
|                              | `new QueueWithPriority<string, string>(System.StringComparer.Ordinal)`                   | `{"Items": [], "PriorityComparer": {"_ignoreCase": false}}`           | Expression | This constructor will use the specified [IComparer][]&lt;[TPriority][]&gt; to order the items in the queue by priority. |

### Known Limitations

None

## See Also

### Related Data Types

* [IComparer][]&lt;[TPriority][]&gt;

### Related Concepts

None

### External Documentation

* [System.Collections.Generic.PriorityQueue&lt;TElement,TPriority>][PriorityQueue]

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
