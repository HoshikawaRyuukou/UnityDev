- [Manual](https://vcontainer.hadashikick.jp/)


> đ«:  InvalidOperationException: ValueFactory attempted to access the Value property of this instance. 
> 
> éçŒçćšćèć°èȘć·±çææł

```csharp
public class Foo : IHandler
{
    private readonly IEnumerable<IHandler> handlers;

    public Foo(IEnumerable<IHandler> handlers...
}
```

