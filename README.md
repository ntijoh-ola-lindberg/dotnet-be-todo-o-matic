# Dotnet backend for Todo-o-matic

Dotnet backend with Postgres database running in Docker

---

Installera dotnet 7: Installera Software Developer Kit (v7): `brew install dotnet-sdk`

Skapa demoprojekt:
```
dotnet new webapi -o TodoApi
cd TodoApi
dotnet add package Microsoft.EntityFrameworkCore.InMemory
code -r ../TodoApi
```

Hela guiden finns på: https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio-code

Installera Docker: `brew install —cask docker`

Installera Postgres i Docker: https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198

 ~~Skapa tabell i databasen: `create table todos(id serial, title varchar(255), completed boolean);`~~

Installera Postgress Entity Framework Core provider med nuget: `dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL`

Generera och kör en migrations-fil från modell-filerna:
```
dotnet tool install --global dotnet-ef
dotnet ef migrations add InitialCreate
dotnet ef database update
```

Lägg till CORS: https://learn.microsoft.com/en-us/aspnet/core/security/cors?view=aspnetcore-7.0#cors-with-named-policy-and-middleware 

Testa din webservice: http://localhost:5150/swagger/index.html 
PostgreSQL Management Tool för VSCode: https://marketplace.visualstudio.com/items?itemName=ckolkman.vscode-postgres 
