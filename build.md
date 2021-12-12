# Build log Glarf

add dependencies in package manager:

- Install `Microsoft.AspNetCore.Authentication.Google`

add Google oauth clientid and secret to secrets.json

- `dotnet user-secrets set "Authentication:Google:ClientId" "<client-id>"`
- `dotnet user-secrets set "Authentication:Google:ClientSecret" "<client-secret>"`

apply migrations:

- `dotnet ef database update`

add redirect URIs to oauth providers console:

- <https://console.cloud.google.com/apis/credentials?project=project-id-5492027856656967194>

switch to postgres

- appsettings connectionstring: `"DefaultConnection": "Server=localhost;Port=5432;Database=postgres;User Id=postgres;Password=postgres;"`
- Add `Npgsql.EntityFrameworkCore.PostgreSQL` package
- Delete your "Migrations" folder.
- Run `dotnet ef migrations add InitialCreate -o Data\Migrations`
- Then `dotnet ef database update`
