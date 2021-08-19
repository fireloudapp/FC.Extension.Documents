---
description: Truncate a string  with a specified Length
---

# Truncate a String

## Truncate

The below method truncates a string to a given specified length

### Package

```
Install-Package FC.Core.Extension -Version 5.0.1
```

### Sample Code

```csharp
[Theory]
[InlineData("This was the value to be truncted", 5)]
[InlineData("Truncated output", 10)]

public void TruncateTest_Test(string value, int length)
{
    string output = value.Truncate(length);            
    _output.WriteLine(output);
    output.ShouldNotBeEmpty();
}
```

### Output

![](../.gitbook/assets/image%20%282%29.png)

![](../.gitbook/assets/image%20%283%29.png)

