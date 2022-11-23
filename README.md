# .NET backend for Todo-o-matic

Backend using .NET v7 with Postgres DB running in Docker.   
Demo project that replaces Todo-o-matic Sinatra backend.

---

## Install + getting started

1. **Install .NET 7 SDK** (Software Developer Kit): `brew install dotnet-sdk`

2. **Create demo project:**
    ```
    dotnet new webapi -o TodoApi 
    cd TodoApi 
    dotnet add package Microsoft.EntityFrameworkCore.InMemory 
    code -r ../TodoApi
    ```

    *Complete guide for installing .NET with demo project: https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio-code*

3. **Install Docker:** `brew install —cask docker`

4. **Install Postgres Docker image:** https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198

    *Start Docker container with persistent data on disk:* `docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres`

5. **Install Postgress Entity Framework Core provider with NuGet:** `dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL`

6. **Create your model files.** See *this* demo project.

7. **Generate and run DB migration files from modell classes**
    ```
    dotnet tool install --global dotnet-ef
    dotnet ef migrations add InitialCreate
    dotnet ef database update
    ```

8. **Add CORS exception for localhost:** https://learn.microsoft.com/en-us/aspnet/core/security/cors?view=aspnetcore-7.0#cors-with-named-policy-and-middleware 

## Tools

* **Test your web service with Swagger:** http://localhost:5150/swagger/index.html  

* **PostgreSQL Management Tool för VSCode:** https://marketplace.visualstudio.com/items?itemName=ckolkman.vscode-postgres

* **C# REPL:** https://github.com/waf/CSharpRepl

* **Uninstall tool for .NET:** https://learn.microsoft.com/en-us/dotnet/core/additional-tools/uninstall-tool?tabs=macos 
