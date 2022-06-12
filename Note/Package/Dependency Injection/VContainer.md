- [Manual](https://vcontainer.hadashikick.jp/)


> 🚫:  InvalidOperationException: ValueFactory attempted to access the Value property of this instance. 
> 
> 這發生在參考到自己的情況

```csharp
public class Foo : IHandler
{
    private readonly IEnumerable<IHandler> handlers;

    public Foo(IEnumerable<IHandler> handlers...
}
```

