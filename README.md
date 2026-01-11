> [!Architecture]

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

1. For **Layered** Architecture Repository Interfaces placed in $${\color{blue} Domain }$$ $${\color{blue} layer }$$, ExternalSystems interfaces in $${\color{blue} Application }$$ $${\color{blue} layer }$$.
2. For **Hexagonal** Architecture RepositoryAndExternalSystems Interfaces placed in separate project as $${\color{blue} Ports }$$ $${\color{blue} layer }$$.
3. For **Clean** and **Onion** Archtecture RepositoryAndExternalSystems Interfaces is placed in $${\color{blue} UseCase }$$ $${\color{blue} layer }$$ or $${\color{blue} Application }$$ $${\color{blue} layer }$$.

<br />

What are the interfaces present in **RepositoryAndExternalSystems** Interfaces

```typescript

Repository Interfaces

1. IUnitOFWork
2. ITransaction
3. IRepository
4. I{Entity}Repository

ExternalSystems Interfaces

5. IEmailService
6. ILoggingService
7. IPaymentService
8. IExternalSystemInterfaces

```


