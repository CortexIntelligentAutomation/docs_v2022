---
title: "StringComparer"
linkTitle: "StringComparer"
description: "Used to compare two pieces of text against each other."
---

# {{% param title %}}

<p class="namespace">(System.StringComparer)</p>

<img src="/images/work-in-progress.jpg">

## Summary

The `StringComparer` data type is used to represent a string comparer.

| | |
|-|-|
| **Category:**          | Text                                                          |
| **Name:**              | `StringComparer`                                                      |
| **Full Name:**         | `System.StringStringComparer`                                               |
| **Alias:**             | N/A                                                    |
| **Description:**       | Used to represent a string comparer. |
| **Default Value:**     | `null`                                                           |
| **Can be used as:**    | `Object`                                                         |
| **Can be cast to:**    | `IComparer`, `IComparer<T>`, `IEqualityComparer`, `IEqualityComparer<T>`                                                             |

## Properties

### CurrentCulture

| | |
|-|-|
| **Name:**    | CurrentCulture                                         |
| **Value:**   | `StringComparer.CurrentCulture`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-sensitive string comparison using the word comparison rules of the current culture. |
### CurrentCultureIgnoreCase

| | |
|-|-|
| **Name:**    | CurrentCultureIgnoreCase                                         |
| **Value:**   | `StringComparer.CurrentCultureIgnoreCase`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-insensitive string comparison using the word comparison rules of the current culture. |

### InvariantCulture

| | |
|-|-|
| **Name:**    | InvariantCulture                                         |
| **Value:**   | `StringComparer.InvariantCulture`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-sensitive string comparison using the word comparison rules of the invariant culture. |

### InvariantCultureIgnoreCase

| | |
|-|-|
| **Name:**    | InvariantCultureIgnoreCase                                         |
| **Value:**   | `StringComparer.InvariantCultureIgnoreCase`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-insensitive string comparison using the word comparison rules of the invariant culture. |

### Ordinal

| | |
|-|-|
| **Name:**    | Ordinal                                         |
| **Value:**   | `StringComparer.Ordinal`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-sensitive ordinal string comparison. |

### OrdinalIgnoreCase

| | |
|-|-|
| **Name:**    | Ordinal                                         |
| **Value:**   | `StringComparer.Ordinal`                       |
| **Notes:**   | Gets a StringComparer object that performs a case-insensitive ordinal string comparison. |

## Remarks

### Create a StringComparer

The following table shows some of the ways that `StringComparer` can be created using the expression editor.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Declare a `StringComparer` literal  |  `StringComparer.CurrentCulture`      | `StringComparer.CurrentCulture` | Expression | Gets a StringComparer object that performs a case-sensitive string comparison using the current culture.  |
||  `StringComparer.CurrentCultureIgnoreCase`      | `StringComparer.CurrentCultureIgnoreCase` | Expression | Gets a StringComparer object that performs a case-insensitive string comparison using the current culture.  |
||  `StringComparer.InvariantCulture`      | `StringComparer.InvariantCulture` | Expression | Gets a StringComparer object that performs a case-sensitive string comparison using the invariant culture.  |
||  `StringComparer.InvariantCultureIgnoreCase`      | `StringComparer.InvariantCultureIgnoreCase` | Expression | Gets a StringComparer object that performs a case-insensitive string comparison using the invariant culture.  |
||  `StringComparer.Ordinal`      | `StringComparer.Ordinal` | Expression | Gets a StringComparer object that performs a case-sensitive string comparison using the current culture.  |
||  `StringComparer.OrdinalIgnoreCase`      | `StringComparer.OrdinalIgnoreCase` | Expression | Gets a StringComparer object that performs a case-insensitive ordinal string comparison.  |

### Convert StringComparer to Text

The following table shows some of the ways that a `StringComparer` can be converted to text.

| Method | Example | Result | Editor&nbsp;Support | Notes |
|-|-|-|-|-|
| Use `ToString`   |  `StringComparer.Ordinal.ToString()`      | `"System.OrdinalCaseSensitiveComparer"` | Expression | Converts `StringComparer.Ordinal` to `"System.OrdinalCaseSensitiveComparer"`.  |
||  `StringComparer.OrdinalIgnoreCase.ToString()`      | `"System.OrdinalIgnoreCaseComparer"` | Expression | Converts `StringComparer.Ordinal` to `"System.OrdinalIgnoreCaseComparer"`.  |
||  `StringComparer.CurrentCulture.ToString()`      | `"System.CultureAwareComparer"` | Expression | Converts `StringComparer.Ordinal` to `"System.CultureAwareComparer"`.  |
||  `StringComparer.CurrentCultureIgnoreCase.ToString()`      | `"System.CultureAwareComparer"` | Expression | Converts `StringComparer.CurrentCulture` to `"System.CultureAwareComparer"`.  |
||  `StringComparer.InvariantCulture.ToString()`      | `"System.CultureAwareComparer"` | Expression | Converts `StringComparer.InvariantCulture` to `"System.CultureAwareComparer"`.  |
||  `StringComparer.InvariantCultureIgnoreCase.ToString()`      | `"System.CultureAwareComparer"` | Expression | Converts `StringComparer.InvariantCultureIgnoreCase` to `"System.CultureAwareComparer"`.  |

### Property Editor Support

### Known Limitations

## See Also

### Related Data Types

### Related Concepts

### External Documentation
