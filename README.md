# Clean-Architecture
This repository is discuss about Clean architecture by using technology asp.net core and angular.
Solution consists of following projects 
1. Entities
2. UseCase or BusinessService
3. Infrastructure
4. Controller

Clean Architecture Dependency travels towards inwards with DDD (Domain Driven Design)

<br />

Dependency Layer
-----------------------

```nginx

   UseCase --> Entities
   Infrastructure --> UseCase
                  --> Entities
   Controller --> UseCase
              --> Refers Infrastrucure only for Composition Root.

```
<br />

```nginx

1. Entities or Domain project
      will have only about Entities or Domain
      Value Objects
      Aggregate Root
```

```nginx

2. UseCase or Business Service project
      will have infrastructure interfaces like Repository interfaces
      will have services interfaces
      will have usecase interfaces
      unitofwork interfaces
      transaction interfaces
      usecase implementation with internal access specifiers
      expose only interfaces and composition root using public access specifiers
      usecase implementation should have transactions implemented using IUnitOFWork and ITransaction interface

```

```nginx

3. Infrastructure Project
      Should have implementation for Repositories.
      Should have implementation for Transaction.
      Should have implementation for UnitOfWork.
      Should have implementation for Services.
      All the above four are with internal access specifiers.
      Expose CompositeRoot to register the Dependency injection.

```

```nginx

4. Controller Project
       Should register the services in program.cs
       refer the usecase service and call it.

```
   
