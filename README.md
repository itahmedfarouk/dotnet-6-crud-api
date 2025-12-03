# .NET 6 CRUD API Example 🚀

A clean and simple **CRUD Web API** built with **ASP.NET Core .NET 6**.  
This repo is a practical starter template showing a layered approach (Controllers → Services → Entities/Models) with centralized error handling and Swagger support.

> Forked & adapted from Jason Watmore's .NET 6 CRUD API tutorial.

## ✨ Features

- Full CRUD operations (Create / Read / Update / Delete)
- RESTful API design + clear routing
- Service layer (business logic separated from controllers)
- DTOs for request/response shaping
- Centralized error handling with consistent responses
- Configuration via `appsettings.json`
- Swagger / OpenAPI enabled in Development
- Easy to extend with EF Core, Authentication, Docker, etc.

## 🧱 Tech Stack

- .NET 6
- ASP.NET Core Web API
- Built-in Dependency Injection
- Swagger (Swashbuckle)

## 📁 Project Structure

```
dotnet-6-crud-api/
│
├── Controllers/        # API endpoints
├── Services/           # Business logic + user service
├── Entities/           # Domain entities
├── Models/Users/       # DTOs (requests/responses)
├── Helpers/            # App settings, middleware, utilities
│
├── Program.cs          # App bootstrap + DI + middleware pipeline
├── WebApi.csproj       # Project config
└── appsettings.json    # App configuration
```

## ✅ Prerequisites

- Install .NET 6 SDK:  
  https://dotnet.microsoft.com/download/dotnet/6.0

## ⚙️ Run Locally

1. Clone the repo
   ```bash
   git clone https://github.com/itahmedfarouk/dotnet-6-crud-api.git
   cd dotnet-6-crud-api
   ```

2. Restore packages
   ```bash
   dotnet restore
   ```

3. Run the API
   ```bash
   dotnet run
   ```

4. Open Swagger UI
   - https://localhost:5001/swagger  
   - or http://localhost:5000/swagger  

> Ports may differ depending on your environment. Check console output.

## 🔌 API Endpoints (Users)

Base path: `/users`

| Method | Endpoint        | Description          |
|-------:|-----------------|----------------------|
| GET    | `/users`        | Get all users        |
| GET    | `/users/{id}`   | Get user by id       |
| POST   | `/users`        | Create a user        |
| PUT    | `/users/{id}`   | Update a user        |
| DELETE | `/users/{id}`   | Delete a user        |

## 📦 Example Requests

### Create User — `POST /users`

```json
{
  "title": "Mr",
  "firstName": "Ahmed",
  "lastName": "Farouk",
  "email": "ahmed@example.com",
  "password": "Secret123!"
}
```

### Update User — `PUT /users/{id}`

```json
{
  "title": "Eng",
  "firstName": "Ahmed",
  "lastName": "Farouk",
  "email": "ahmed@example.com"
}
```

## ✅ Example Responses

### Success

```json
{
  "id": 1,
  "title": "Mr",
  "firstName": "Ahmed",
  "lastName": "Farouk",
  "email": "ahmed@example.com"
}
```

### Error

```json
{
  "message": "User not found"
}
```

## 🧠 Architectural Notes

### Controllers
- Handle routing + validation
- Keep endpoints thin
- Delegate all logic to services

### Services
- Business rules
- Data operations
- Validations & edge cases

### Entities vs DTOs
- Entities represent core domain objects
- DTOs/Models represent request & response contracts  
  (prevents over-posting & hides internal fields)

## 🛠️ Extend This Template

Common upgrades you can add easily:

- EF Core + Database (SQL Server / PostgreSQL / SQLite)
- JWT Authentication + Authorization
- AutoMapper for DTO mapping
- Serilog logging
- Docker support
- Unit Tests (xUnit)

## 🤝 Contributing

Pull requests are welcome.  
For major changes, open an issue first to discuss what you want to add.

## 📜 License

MIT License — free to use, modify, and distribute.

## ⭐ Acknowledgements

Inspired by the original tutorial & structure by **Jason Watmore**:  
https://jasonwatmore.com/post/2022/03/15/net-6-crud-api-example-and-tutorial
