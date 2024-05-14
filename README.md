# Motorcycle Rental

Backend system for managing motorcycle rentals.

API built in .Net 8, following a Clean Architecture structure divided into 4 layers: Domain, Application, Infrastructure, and Presentation(API).

## Main resources used:

- ORM with EntityFramework
- CQRS with MediatR
- Security (Authentication and Authorization) with AspNetCore Identity and JWT
- Testing with Xunit
- Logging (Console and file) with Serilog
- Image handling with AWS S3
- Message Broker with RabbitMQ
- Documentation with Swagger
- Containerization with Docker Compose and Docker
- Postgres Database

## Project Composition

- Postgres - Relational Database Server
- PGAdmin - DBMS for Postgres management
- RabbitMQ - Message Broker
- Worker - RabbitMQ Consumer
- Motorcycle Rental API

## Execution

#### With Docker installed, run the following command in the project root directory:

```bash
docker-compose up -d
```

#### This command will initialize 3 services:

- Postgres (localhost:5432)
- PGAdmin (http://localhost:8081)
- RabbitMQ. AMQP server (localhost:5672) and Dashboard(http://localhost:15672)

#### You can start the Worker and the API directly in Visual Studio or using the .Net CLI

##### API:

```bash
dotnet run --project .\src\MotorcycleRental.API\MotorcycleRental.API.csproj --urls="https://localhost:5001;http://localhost:5000"
```

*A API estará dispinível através da URL https://localhost:5001/swagger e poderá ser acessada pelo browser de sua preferencia.

##### Worker(RabbitMQ Consumer):

```bash
dotnet run --project .\src\MotorcycleRentMessageBrokerConsumer1\
```

## Migrations e Seeds

To facilitate execution, testing, and deployment, automatic database structure creation using Migrations has been implemented. The Seeds feature was also used to insert the following basic records:

- Planos de Locação
- Usuários: Admin e Biker(Entregador)
- Roles: Admin e Biker
- Dois registros de motos de exemplo




