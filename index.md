---
layout: default
---

![Nuget](https://img.shields.io/nuget/v/OpenSleigh.Core?style=plastic)
[![OpenSleigh](https://circleci.com/gh/mizrael/OpenSleigh.svg?style=shield&circle-token=b7635df8feb7c79524db993c3cf962863ad28aa1)](https://app.circleci.com/pipelines/github/mizrael/OpenSleigh)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=mizrael_OpenSleigh&metric=coverage)](https://sonarcloud.io/dashboard?id=mizrael_OpenSleigh)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=mizrael_OpenSleigh&metric=security_rating)](https://sonarcloud.io/dashboard?id=mizrael_OpenSleigh)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=mizrael_OpenSleigh&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=mizrael_OpenSleigh)

OpenSleigh is a distributed saga management library, written in C# with .NET Core. 
It is intended to be reliable, fast, easy to use, configurable and extensible.

## What?
So what is a Saga exactly? The basic idea is quite interesting: in a micro-service architecture, it often happens that we need to manage several long-running operations that span multiple services. 

A good example could be an Order processing workflow: in this scenario you have to orchestrate multiple services, doing inventory management, credit check, handling shipping and so on.   

OpenSleigh helps by taking care of [distributed transactions](https://www.davideguida.com/improving-microservices-reliability-part-1-two-phase-commit/), keeping track of the global status and managing the whole flow.

## Installation
The Core module is available [on Nuget](https://www.nuget.org/packages/OpenSleigh.Core/).
However, a Transport and Persistence library are necessary to properly use the library.

These are the libraries available at the moment:
- [InMemory](https://www.nuget.org/packages/OpenSleigh.Persistence.InMemory/)
- [MongoDB](https://www.nuget.org/packages/OpenSleigh.Persistence.Mongo/)
- [MSSQL](https://www.nuget.org/packages/OpenSleigh.Persistence.SQL/)
- [Azure Service Bus](https://www.nuget.org/packages/OpenSleigh.Transport.AzureServiceBus/)
- [RabbitMQ](https://www.nuget.org/packages/OpenSleigh.Transport.RabbitMQ/)

## Roadmap
- add CosmosDB saga state persistence

## Issues? Questions? Suggestions?
Feel free to [reach out](https://github.com/mizrael/OpenSleigh/discussions) and tell us what you think!