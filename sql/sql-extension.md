---
description: 'An extension of SQL Style of Database, SQL Server, PostgreSQL, SQLite & MySQL'
---

# SQL Extension

## Introduction

This Extension library uses the RepoDB as a primary Database Access, on top this an extension method has been added to avoid repeated code, which is easy for development team to focus on the core operation.

```scheme
Install-Package FC.Extension.SQL
```

{% hint style="info" %}
 The above will install the latest package from the nuget.

Through out this Data Access Example I have used a model called "Person" below is the full code for the class Person.
{% endhint %}

```csharp
public class Person
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Email { get; set; }   
}
```

### A Main Method which invokes all the command

```csharp
public static class Program
{
    public static async Task<int> Main() =>
        await new CliApplicationBuilder()
            .AddCommandsFromThisAssembly()
            .Build()
            .RunAsync();
}
```

{% hint style="info" %}
All source code can be found in [Github Repository](https://github.com/fireloudapp/FC.Extension.SQL)
{% endhint %}



