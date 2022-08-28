Rest-Dot-Net-core
This is a solution template for creating a Single Page App (SPA) with Angular and ASP.NET Core following the principles of Clean Architecture.

Technologies
ASP.NET Core 3.1
Entity Framework Core 3.1
MediatR
AutoMapper
FluentValidation
NUnit, FluentAssertions, Moq & Respawn
Docker
Seri Logger
API Versioning
Swagger UI.
JWT Token Authentication
Global Error Handler Middleware
CQRS ( Command Query Responsibility Segregation)
Generic Repository Pattern
Build & Run
Change Connectionstring in appsettings.json

Run below commands in Package manager console

1 update-database -Context GloboTicketIdentityDbContext

2 update-database -Context GloboTicketDbContext



Overview





Domain
This will contain all entities, enums, exceptions, interfaces, types and logic specific to the domain layer.

Application
This layer contains all application logic. It is dependent on the domain layer, but has no dependencies on any other layer or project. This layer defines interfaces that are implemented by outside layers. For example, if the application need to access a notification service, a new interface would be added to application and an implementation would be created within infrastructure.

Infrastructure
This layer contains classes for accessing external resources such as file systems, web services, smtp, and so on. These classes should be based on interfaces defined within the application layer.

WebUI
This layer is a single page application based on Angular/React and ASP.NET Core 3.1. This layer depends on both the Application and Infrastructure layers, however, the dependency on Infrastructure is only to support dependency injection. Therefore only Startup.cs should reference Infrastructure.

License
This project is licensed with the MIT license.
