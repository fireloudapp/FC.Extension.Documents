# ToDataTable

## ToDataTable

The below method which converts List to DataTable

### Package

```
Install-Package FC.Core.Extension -Version 5.0.1
```

### Sample Code

```csharp
IList<DummyData> dummies = new List<DummyData>();
dummies.Add(dummy1);
dummies.Add(dummy2);

var dtList = dummies.ToDataTable<DummyData>();
dtList.Rows.Count.ShouldBeGreaterThan(1);
```

### Output

![Output of ToDataTable after Execution](../.gitbook/assets/image%20%281%29.png)



