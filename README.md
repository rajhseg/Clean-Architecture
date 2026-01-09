# Hexagonal-Architecture
This repository is discuss about Hexagonal architecture by using technology Asp.Net Core and Angular.
Solution consists of following projects 

1. Entities
2. BusinessService.ExternalSystems.Contracts ((Ports) separate project for application layer interface)
3. UseCase or BusinessService
4. Infrastructure
5. Controller

Hexagonal Architecture Dependency travels towards inwards

<br />

<br />

Dependency Layer
-----------------------

```nginx

   Entities

   UseCaseExternalSystemInterfaces

   UseCase  --> Entities
            --> UseCaseExternalSystemInterfaces

   Infrastructure --> Entities
                  --> UseCaseExternalSystemInterfaces

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
<br />

```nginx

2. UseCaseExternalSystemInterfaces

   
      will have External System Services interfaces (ex IEmailService)


      will have External System Contracts or interfaces (ex IPaymentServiceGateway
            or IAddressValidate)

```
<br />

```nginx

3. UseCase or Business Service project

      will have usecase interfaces (ex IAuthorService)

      usecase implementation with internal access specifiers (ex internal class AuthorService)

      expose only interfaces and composition root using public access specifiers
            (ex IAuthorService, RegistorService())

      usecase (AuthorService) implementation should have transactions implemented
         using IUnitOFWork interface

```


```nginx

4. Infrastructure Project

      Should have implementation for Repositories. (ex AuthorRepository)

      Should have implementation for Transaction. (ex EFTransaction)

      Should have implementation for UnitOfWork. (ex UnitOfWork)

      Should have implementation for External Services. (ex EmailService)

      Should have implementation for UseCaseExternalSystemInterfaces.
         (ex PaymentServiceGateway or AddressValidate) 

      All the above four are with internal access specifiers.

      Expose CompositeRoot to register the Dependency injection. (RegisterRepositories() method)

```

```nginx

5. Controller Project

       Should register the services in program.cs

       refer the usecase service and call it.

```
   
