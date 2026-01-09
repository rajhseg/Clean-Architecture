# Architectures

This repository will discuss about the different architectures present in software.
Currently it have below items

1. Layered Architecture
2. Onion Architecture
3. Hexagonal Architecure
4. Clean Architecture

Solution consists of following projects

```typescript

1. Entities or Domain
2. UseCase or BusinessService or Application Layer
3. Infrastructure
4. Controller

5. Ports (only for Hexagonal arch project)

```

Architecures are differ based on the **RepositoryAndExternalSystems** Interfaces placed

1. For **Layered** Architecure **RepositoryAndExternalSystems** Interfaces placed in **Domain layer**.
2. For **Hexagonal** Architecture **RepositoryAndExternalSystems** Interfaces placed in separate project as **Ports layer**.
3. For **Clean** and **Onion** Archtecture **RepositoryAndExternalSystems** Interfaces is placed in **UseCase or Application layer**.

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


