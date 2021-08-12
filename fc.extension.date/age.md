---
description: Calculate Age
---

# Age

## Age Calculation

Calculate Age based

```csharp
using FC.Core.Extension.DateHandlers;


DateTime dtAge = new DateTime(2016, 02, 25);
int age = dtAge.Age();           
_output.WriteLine($"Age of person born at {dtAge.ToLongDateString()} is '{age}'");

```

## Get Age & Month

```csharp
using FC.Core.Extension.DateHandlers;

DateTime dtAge = new DateTime(2016, 02, 25);
int age = dtAge.Age();
double month = dtAge.AgeInMonth();
_output.WriteLine($"Age of person born at {dtAge.ToLongDateString()} is '{age}' Month {month}");
```



