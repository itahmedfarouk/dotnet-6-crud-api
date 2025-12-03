# .NET 6 CRUD API (Clean Architecture-ish) 🚀

A simple, production-ready **CRUD Web API** built with **ASP.NET Core .NET 6**.  
The project demonstrates a clean and scalable structure using Controllers, Services, Entities/Models, and Helpers — perfect as a starter template for real-world APIs.

> Forked & adapted from the original tutorial by Jason Watmore.  
> Docs: https://jasonwatmore.com/post/2022/03/15/net-6-crud-api-example-and-tutorial

---

## ✨ Features

- Full CRUD operations (Create / Read / Update / Delete)
- RESTful endpoints following clean conventions
- Service layer separation (business logic isolated from controllers)
- DTOs/Models for request & response shaping
- Centralized error handling with consistent API responses
- Configuration via `appsettings.json`
- Swagger / OpenAPI ready (enabled in development)
- Easy to extend with Authentication, EF Core, or any persistence layer

---

## 🧱 Tech Stack

- **.NET 6**
- **ASP.NET Core Web API**
- Dependency Injection (built-in)
- Swagger / Swashbuckle (Dev)
- Clean layered structure

---

## 📁 Project Structure

```

dotnet-6-crud-api/
│
├── Controllers/     # API endpoints
├── Services/        # Business logic + data access abstraction
├── Entities/        # Core domain entities
├── Models/Users/    # DTOs (requests/responses) related to users
├── Helpers/         # Utilities (error handling, settings, etc.)
│
├── Program.cs       # App bootstrap + DI + middleware
├── WebApi.csproj    # Project file
└── appsettings.json # App configuration

````

---

## ✅ Prerequisites

Make sure you have:

- **.NET 6 SDK** installed  
  Download: https://dotnet.microsoft.com/en-us/download/dotnet/6.0

---

## ⚙️ Setup & Run

1. **Clone the repo**
   ```bash
   git clone https://github.com/itahmedfarouk/dotnet-6-crud-api.git
   cd dotnet-6-crud-api
````

2. **Restore packages**

   ```bash
   dotnet restore
   ```

3. **Run the API**

   ```bash
   dotnet run
   ```

4. **Open Swagger UI**

   * Usually at:
     `https://localhost:5001/swagger`
     or
     `http://localhost:5000/swagger`

> If ports differ, check the console output when the app starts.

---

## 🔌 API Endpoints (Example – Users)

> Base URL: `/users`

| Method | Endpoint      | Description          |
| -----: | ------------- | -------------------- |
|    GET | `/users`      | Get all users        |
|    GET | `/users/{id}` | Get user by id       |
|   POST | `/users`      | Create new user      |
|    PUT | `/users/{id}` | Update existing user |
| DELETE | `/users/{id}` | Delete user          |

### Sample `POST /users` Body

```json
{
  "title": "Mr",
  "firstName": "Ahmed",
  "lastName": "Farouk",
  "email": "ahmed@example.com",
  "password": "Secret123!"
}
```

### Sample Success Response

```json
{
  "id": 1,
  "title": "Mr",
  "firstName": "Ahmed",
  "lastName": "Farouk",
  "email": "ahmed@example.com"
}
```

---

## 🧠 How It Works

### Controllers

Controllers are thin and only handle:

* routing
* validation
* returning HTTP responses

They delegate all real work to services.

### Services

Services contain:

* core business logic
* data handling
* validations & edge cases

This makes the API easier to test and maintain.

### Entities & Models

* **Entities** represent the domain objects.
* **Models/DTOs** represent request/response contracts.

---

## 🧯 Error Handling

Errors are handled centrally to keep responses consistent.

Example error response:

```json
{
  "message": "User not found"
}
```

---

## 🧪 Testing Tips

You can test endpoints using:

* Swagger UI
* Postman
* cURL

Example:

```bash
curl -X GET https://localhost:5001/users
```

---

## 🛠️ Customization Ideas

Want to level it up? Add:

* ✅ EF Core + SQL Server / PostgreSQL
* ✅ JWT Authentication
* ✅ Role-based authorization
* ✅ Docker support
* ✅ Logging (Serilog)
* ✅ Unit tests (xUnit)

---

## 🤝 Contributing

PRs are welcome.
If you plan to add a big feature, open an issue first to discuss it.

---

## 📜 License

This project is licensed under the MIT License — feel free to use it anywhere.

---

## ⭐ Acknowledgements

* Original project & tutorial: Jason Watmore
  [https://jasonwatmore.com/post/2022/03/15/net-6-crud-api-example-and-tutorial](https://jasonwatmore.com/post/2022/03/15/net-6-crud-api-example-and-tutorial)


[1]: https://github.com/itahmedfarouk/dotnet-6-crud-api "GitHub - itahmedfarouk/dotnet-6-crud-api: .NET 6.0 - CRUD API Example"
