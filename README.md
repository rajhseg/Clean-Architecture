# Architectures

This repository will discuss about the different architectures present in software.
Currently it have below items

1. Layered Architecture
2. Onion Architecture
3. Hexagonal Architecure
4. Clean Architecture

Architecures are differ based on the **RepositoryAndExternalSystems** Interfaces placing

1. For Layered and Onion Architecure **RepositoryAndExternalSystems** Interfaces placed in **Domain layer**.
2. For Hexagonal Architecture **RepositoryAndExternalSystems** Interfaces is placed in separate project as **Ports layer**.
3. For Clean Archtecture **RepositoryAndExternalSystems** Interfaces is placed in **UseCase layer**.

<br />

What are the interfaces present in **RepositoryAndExternalSystems** Interfaces

```typescript

1. IUnitOFWork
2. ITransaction
3. IRepository
4. I{Entity}Repository
5. IEmaiService
6. ILoggingService
7. IPaymentService
8. IExternalSystemInterfaces

```


