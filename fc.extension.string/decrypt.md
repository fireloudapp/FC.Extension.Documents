---
description: >-
  Decrypt a string as a extension method. It uses RSA Standard algorithm to do
  this.
---

# Decrypt

## Method : Decrypt 

```text
[Command("Dec")]
public class DecryptExtension_Command : ICommand
{
    [CommandOption("enc", 'e', Description = "Value that has to be encrypt")]
    public string Value { get; set; }

    [CommandOption("key", 'k', Description = "Key used to encrypt or Decrypt.")]
    public string Key { get; set; }

    public ValueTask ExecuteAsync(IConsole console)
    {
        string encryptedValue = Value.Encrypt(Key);
        string decryptedValue = encryptedValue.Decrypt(Key);
        console.Output.WriteLine($"Plan Text : {Value} Encrypted Value : {encryptedValue} Key : {Key}");
        console.Output.WriteLine($"Encrypted Text : {encryptedValue} Decrypted Value : {decryptedValue} Key : {Key}");
        return default;
    }
}
```

