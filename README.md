# Clean-Architecture
This repository is discuss about Clean architecture by using technology Asp.Net Core and Angular.
Solution consists of following projects 
1. Entities
2. UseCase or BusinessService
3. Infrastructure
4. Controller

Clean Architecture Dependency travels towards inwards with DDD (Domain Driven Design)

<br />

<img width="1120" height="716" alt="image" src="https://github.com/user-attachments/assets/e546a694-1ddf-4705-8099-8c476a7cf24d" />

<br />

<img width="719" height="343" alt="image" src="https://github.com/user-attachments/assets/efc52030-25de-4482-96ab-37e5ff3bb78a" />

<br />
<br />

Dependency Layer
-----------------------

```nginx

   UseCase --> Entities

   Infrastructure --> Entities
                  --> UseCase

   Controller --> Refers UseCase only for Composition Root.
              --> Refers Infrastrucure only for Composition Root.

```
<br />

<br />

```nginx

1. Entities or Domain project

      will have only about Entities or Domain

      Value Objects

      Aggregate Root

      will have infrastructure interfaces like Repository interfaces
            (ex IRepository, IAuthorRepository)

      unitofwork interfaces (ex IUnitOfWork)

      transaction interfaces (ex ITransaction)

```

```nginx

2. UseCase or Business Service project

      will have services interfaces (ex IEmailService)

      will have usecase interfaces (ex IAuthorService)

      will have External Services Contracts or interfaces (ex IPaymentServiceGateway or IAddressValidate)

      usecase implementation with internal access specifiers (ex internal class AuthorService)

      expose only interfaces and composition root using public access specifiers
            (ex IAuthorService, RegistorService())

      usecase (AuthorService) implementation should have transactions implemented
         using IUnitOFWork interface

```


```nginx

3. Infrastructure Project

      Should have implementation for Repositories. (ex AuthorRepository)

      Should have implementation for Transaction. (ex EFTransaction)

      Should have implementation for UnitOfWork. (ex UnitOfWork)

      Should have implementation for Services. (ex EmailService)

      Should have implementation for UseCase Interface. (ex PaymentServiceGateway or AddressValidate) 

      All the above four are with internal access specifiers.

      Expose CompositeRoot to register the Dependency injection. (RegisterRepositories() method)

```

```nginx

4. Controller Project

       Should register the services in program.cs

       refer the usecase service and call it.

```
   
