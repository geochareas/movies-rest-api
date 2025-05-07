
# 🎬 Movies REST API

A simple ASP.NET Core REST API for managing a list of movies. The solution is organized into multiple projects for better separation of concerns.

---

## 📁 Project Structure

```
Movies.sln
│
├── Movies.Api           # ASP.NET Core Web API (controllers, middleware, startup)
├── Movies.Application   # Core business logic (services, interfaces)
└── Movies.Contracts     # Shared DTOs (requests, responses, enums)
```

This structure helps maintain a clean separation between the API layer, application logic, and data contracts.

---

## 🌐 REST API Guidelines

### ✅ Naming & Structure

- Use **plural nouns** for endpoints: `/movies`
- Use standard REST verbs:
  - `GET /movies` – Get all movies
  - `GET /movies/{id}` – Get movie by ID
  - `POST /movies` – Create a movie
  - `PUT /movies/{id}` – Update a movie
  - `DELETE /movies/{id}` – Delete a movie

### ✅ Status Codes

| Status Code | Meaning                        |
|-------------|--------------------------------|
| 200 OK      | Successful response            |
| 201 Created | Resource created               |
| 204 No Content | Resource deleted/updated    |
| 400 Bad Request | Validation or input issue  |
| 404 Not Found | Resource not found           |
| 500 Internal Server Error | Server-side error |

### ✅ Example Error Response

```json
{
  "errors": [
    "Title must not be empty.",
    "Release year must be a valid number."
  ]
}
```


## 🧪 Example Endpoints

### ➕ Create a Movie

**POST** `/movies`

```json
{
  "title": "Interstellar",
  "releaseYear": 2014
}
```

**Response:**

```json
{
  "id": 1,
  "title": "Interstellar",
  "releaseYear": 2014
}
```

---

### 📘 Retrieve All Movies

**GET** `/movies`

**Response:**

```json
[
  {
    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "title": "Interstellar",
    "director": "Christopher Nolan",
    "releaseYear": 2014
  }
]
```


## 📁 Folder Layout (Simplified)

```
Movies.Api/
├── Controllers/
│   └── MoviesController.cs
├── Program.cs
├── appsettings.json

Movies.Application/
├── Services/
│   └── IMovieService.cs
│   └── MovieService.cs
├── Repositories/
│   └── IMovieService.cs
│   └── MovieService.cs
├── Validators/
│   └── ...

Movies.Contracts/
├── Requests/
│   └── CreateMovieRequest.cs
├── Responses/
│   └── MovieResponse.cs
```


