---
layout: default
---

OpenSleigh is a distributed Saga management library, written in C# with .NET Core. 
It is intended to be reliable, fast, easy to use, configurable and extensible.

## What?
So what is a Saga exactly? The basic idea is quite interesting: in a micro-service architecture, it often happens that we need to manage several long-running operations that span multiple services. 

A good example could be an Order processing workflow: in this scenario you have to orchestrate multiple services, doing inventory management, credit check, handling shipping and so on.   

OpenSleigh helps by taking care of [distributed transactions](https://www.davideguida.com/improving-microservices-reliability-part-1-two-phase-commit/){:target="_blank"}, keeping track of the global status and managing the whole flow.

For more details, check the [Use Cases](/use-cases/) page.

## Installation
The Core module is available [on Nuget](https://www.nuget.org/packages/OpenSleigh.Core/).
However, Transport and Persistence packages are necessary to properly use the library.

These are the packages available at the moment:
- [InMemory](https://www.nuget.org/packages/OpenSleigh.Persistence.InMemory/)
- [MongoDB](https://www.nuget.org/packages/OpenSleigh.Persistence.Mongo/)
- [MSSQL](https://www.nuget.org/packages/OpenSleigh.Persistence.SQL/)
- [Azure Service Bus](https://www.nuget.org/packages/OpenSleigh.Transport.AzureServiceBus/)
- [RabbitMQ](https://www.nuget.org/packages/OpenSleigh.Transport.RabbitMQ/)
- [CosmosDB](https://www.nuget.org/packages/OpenSleigh.Persistence.Cosmos/)

## Roadmap
- add support for Kafka
- add support for Postgres

## Issues? Questions? Suggestions?
Feel free to [reach out](https://github.com/mizrael/OpenSleigh/discussions) and tell us what you think!