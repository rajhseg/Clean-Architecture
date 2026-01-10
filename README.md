# Architectures

This repository will discuss about the different architectures present in software.
Currently it have below items

1. Layered Architecture
2. Onion Architecture
3. Hexagonal Architecture
4. Clean Architecture

Solution consists of following projects

```typescript

1. Entities or Domain or Business 
2. UseCase or Application 
3. Infrastructure or DataAccess or Adapters
4. Controller

5. Ports (only for Hexagonal arch project)

```

Architecture are differ based on the **RepositoryAndExternalSystems** Interfaces placed

1. For **Layered** Architecture Repository Interfaces placed in **Domain layer**, ExternalSystems interfaces in **Application layer**.
2. For **Hexagonal** Architecture RepositoryAndExternalSystems Interfaces placed in separate project as **Ports layer**.
3. For **Clean** and **Onion** Archtecture RepositoryAndExternalSystems Interfaces is placed in **UseCase or Application layer**.

<br />

What are the interfaces present in **RepositoryAndExternalSystems** Interfaces

```typescript

Repository Interfaces

1. IUnitOFWork
2. ITransaction
3. IRepository
4. I{Entity}Repository

ExternalSystems Interfaces

5. IEmaiService
6. ILoggingService
7. IPaymentService
8. IExternalSystemInterfaces

```


