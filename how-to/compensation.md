---
layout: default
title: Compensation
---

# [How-to](/how-to/) / Compensation
There might be cases when failures in handling messages need to be handled properly. We could always use a try/catch block of course, but OpenSleigh offers a cleaner alternative. 

By adding the interface `ICompensateMessage<TMessage>` to our Saga class, OpenSleigh knows that in case any exception happens when processing a message of type `TMessage`, it has to execute some compensating operation.

```
public class MyAwesomeSaga :
    Saga<MyAwesomeSagaState>,    
    IHandleMessage<DoSomething>,
    ICompensateMessage<DoSomething>
{
    // code omitted for brevity

    public async Task HandleAsync(IMessageContext<ICompensateMessage> context, CancellationToken cancellationToken = default)
    {
       // something goes wrong here
    }

    public async Task CompensateAsync(ICompensationContext<ICompensateMessage> context, CancellationToken cancellationToken = default)
    {
       // handle the error here
    }
}
```

The `ICompensationContext<TMessage>` instance wraps the `IMessageContext<TMessage>` received previously and the `Exception` that was thrown:

```
public interface ICompensationContext<TM> where TM : IMessage
{
    IMessageContext<TM> MessageContext { get; }
    Exception Exception { get; }
}
```
