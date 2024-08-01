# mvcauth
MVC Auth Dot net core reference

dotnet new mvc --auth Individual

dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.Relational
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet tool install --global dotnet-ef

//update the dbcontext
builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer("Server=localhost;Database=AuthDB;User Id=sa;Password=;TrustServerCertificate=true;"));

//delete the default migrations

dotnet ef migrations add "CreateIdentitySchema"

dotnet ef database update
