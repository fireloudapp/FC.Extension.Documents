---
description: This below example shows how to handle FC Extension for the PostgreSQL
---

# PostgreSQL Extension

## CUD a Model through Extension

The below code shows how to use the FC.Extension.SQL to save an object:

```
person = person.Save().Result;
```

```text
person = person.Update().Result;
```

```text
person = person.Delete().Result;
```

### A Full Working code is shown below

```csharp
[Command("PostgreSQL")]
public class PostgreSQLInsert_Execution : ICommand
{
    [CommandOption("Save", 's', Description = "Save a Person")]
    public bool IsSave { get; set; }

    [CommandOption("Update", 'u', Description = "Update a Person")]
    public bool IsUpdate { get; set; }

    [CommandOption("Delete", 'd', Description = "Delete a Person")]
    public bool IsDelete { get; set; }

    public ValueTask ExecuteAsync(IConsole console)
    {
        var personFake = new Faker<Person>()
             .RuleFor(o => o.Name, f => f.Person.FullName)
             .RuleFor(o => o.Email, f => f.Person.Email);
        var person = personFake.Generate();
        SQLExtension.SQLConfig = new SQLExecutionConfig()
        { Compiler = SQLCompiler.PostgreSQL, 
            ConnectionString = "User Id=FCPos;Password=System@1234;Server=localhost;Port=5432;Database=ExtensionTest;", 
            Trace = null };
        if (IsSave)
        {
            person = person.Save().Result;
            console.Output.WriteLine($"Saved Object : {person.ToJSON<Person>()}");
        }
        else if (IsUpdate)
        {
            person.Id = 1;
            person = person.Update().Result;
            console.Output.WriteLine($"Object Updated : {person.ToJSON<Person>()}");
        }
        else if (IsDelete)
        {
            person.Id = 1;
            int records = person.Delete(person.Id).Result;
            console.Output.WriteLine($"Deleted. No of Records : {records}");
        }

        return default;
    }
}


```

