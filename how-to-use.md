# How to Use?

### How to use the Sample?

* All the below sample may uses the [CliFx ](https://github.com/Tyrrrz/CliFx)/xUnit Test based command to use and run as it is.
* 
The full sample on how it uses the extension is given below

```csharp
using System;
using System.Threading.Tasks;
using CliFx;
using CliFx.Attributes;
using CliFx.Infrastructure;

namespace FC.Extension.ExecutionSample
{
    public static class Program
    {
        public static async Task<int> Main() =>
            await new CliApplicationBuilder()
                .AddCommandsFromThisAssembly()
                .Build()
                .RunAsync();
    }    
}
```



