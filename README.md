# FastAPI Automated CRUD API Framework

A Python-based **REST API development project using FastAPI** that demonstrates automated CRUD route generation, database integration, request validation, pagination, dependency management, OpenAPI documentation, and automated testing.

The project focuses on simplifying the development of RESTful APIs by reducing repetitive CRUD endpoint implementation while maintaining a clean and extensible architecture.

---

## 🚀 Project Overview

Building CRUD APIs traditionally requires developers to implement separate endpoints for creating, retrieving, updating, and deleting database records.

This project demonstrates how **FastAPI** can be used to create reusable CRUD API components and automatically generate REST endpoints for database models.

### CRUD Operations

```text
                 FastAPI Application
                         │
                         ▼
                  CRUD Router
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
        Create         Read           Update
          │              │              │
          └──────────────┼──────────────┘
                         ▼
                       Delete
                         │
                         ▼
                    Database
```

---

## 🎯 Objectives

The main objectives of this project are to:

* Develop RESTful APIs using FastAPI
* Automate CRUD endpoint generation
* Integrate APIs with relational databases
* Implement request and response validation
* Implement pagination
* Manage API dependencies
* Generate OpenAPI documentation
* Support multiple database backends
* Implement API testing
* Handle database integrity errors
* Build reusable API components
* Follow modular Python application architecture

---

## 🛠️ Technologies Used

### Backend

* Python
* FastAPI
* Starlette
* Pydantic

### Database & ORM

* SQLAlchemy
* SQLite
* PostgreSQL
* Tortoise ORM
* Ormar
* GINO

### API & Documentation

* REST API
* CRUD
* OpenAPI
* Swagger UI
* ReDoc

### Testing

* Pytest
* Integration Testing
* API Testing

### Development

* Git
* GitHub
* Docker
* Docker Compose
* Python Virtual Environment

---

## ✨ Key Features

### 🔹 Automated CRUD Routes

Automatically creates common REST API operations:

```text
POST    /items
GET     /items
GET     /items/{id}
PUT     /items/{id}
PATCH   /items/{id}
DELETE  /items/{id}
```

This reduces repetitive endpoint implementation.

---

### 🔹 Create

Create new records through REST API requests.

```http
POST /items
```

Example request:

```json
{
    "name": "Laptop",
    "price": 65000
}
```

---

### 🔹 Read

Retrieve all records:

```http
GET /items
```

Retrieve an individual record:

```http
GET /items/1
```

---

### 🔹 Update

Update an existing record:

```http
PUT /items/1
```

Partial updates can also be supported using:

```http
PATCH /items/1
```

---

### 🔹 Delete

Delete an existing record:

```http
DELETE /items/1
```

---

## 📊 Pagination

The API supports pagination for efficiently handling large datasets.

Example:

```http
GET /items?skip=0&limit=10
```

Pagination helps reduce response size and improves API performance when working with large datasets.

---

## 🔐 Dependency Management

FastAPI dependency injection is used to manage reusable API dependencies.

Dependencies can be applied:

* Globally
* Per router
* Per endpoint

This allows authentication, authorization, database sessions, and other shared functionality to be integrated cleanly.

---

## 🗄️ Database Support

The project demonstrates integration with multiple database backends.

### Supported Backends

```text
SQLAlchemy
    │
    ├── SQLite
    ├── PostgreSQL
    └── Other SQL databases

Additional ORM support
    │
    ├── Tortoise ORM
    ├── Ormar
    └── GINO
```

This makes the architecture flexible for different application requirements.

---

## 📚 API Documentation

FastAPI automatically generates interactive API documentation.

After starting the application, documentation can be accessed through:

```text
/docs
```

Swagger UI provides an interactive interface for:

* Viewing endpoints
* Understanding request schemas
* Testing API requests
* Viewing response models

Alternative documentation:

```text
/redoc
```

---

## 🧪 Testing

The project includes a comprehensive testing structure using **Pytest**.

Testing covers areas such as:

* CRUD operations
* API routing
* Pagination
* Primary keys
* Custom IDs
* Dependencies
* OpenAPI schemas
* Database integrity
* Multiple routers
* Backend integrations
* Error handling

Example:

```bash
pytest
```

---

## 📂 Project Structure

```text
fastapi-automated-crud-api/
│
├── fastapi_crudrouter/
│   ├── __init__.py
│   │
│   └── core/
│       ├── __init__.py
│       ├── _base.py
│       ├── _types.py
│       ├── _utils.py
│       ├── databases.py
│       ├── gino_starlette.py
│       ├── mem.py
│       ├── ormar.py
│       ├── sqlalchemy.py
│       └── tortoise.py
│
├── tests/
│   ├── conftest.py
│   ├── test_base.py
│   ├── test_router.py
│   ├── test_pagination.py
│   ├── test_dependencies/
│   ├── test_integration/
│   └── implementations/
│
├── docs/
│   └── en/
│
├── requirements.txt
├── setup.py
├── setup.cfg
├── LICENSE
├── CONTRIBUTING.md
└── README.md
```

---

# 🔄 API Architecture

The application follows a layered architecture:

```text
Client
   │
   ▼
FastAPI
   │
   ▼
CRUD Router
   │
   ├── Request Validation
   │
   ├── Dependency Injection
   │
   ├── CRUD Operations
   │
   ├── Pagination
   │
   └── Error Handling
   │
   ▼
ORM / Database Layer
   │
   ▼
Database
```

---

# 💻 Installation

## Prerequisites

Install:

* Python 3.8+
* pip
* Git

Optional:

* PostgreSQL
* Docker
* Docker Compose

---

## Clone the Repository

```bash
git clone https://github.com/<your-username>/fastapi-automated-crud-api.git
```

Navigate into the project:

```bash
cd fastapi-automated-crud-api
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

For development and testing:

```bash
pip install pytest
```

---

# ▶️ Running a FastAPI Application

A typical FastAPI application can be started using:

```bash
uvicorn main:app --reload
```

The application will then be available locally.

Open the interactive API documentation at:

```text
http://127.0.0.1:8000/docs
```

---

# 🧪 Running Tests

Execute the test suite with:

```bash
pytest
```

For more detailed output:

```bash
pytest -v
```

---

# 📌 Example CRUD API

A basic FastAPI application can expose CRUD operations through a router.

Conceptually:

```text
POST    /users
GET     /users
GET     /users/{id}
PUT     /users/{id}
PATCH   /users/{id}
DELETE  /users/{id}
```

The router handles the underlying CRUD operations while FastAPI manages request validation and API documentation.

---

# 📈 Benefits

The approach demonstrated by this project provides several advantages:

* Reduced repetitive CRUD code
* Faster API development
* Consistent endpoint structure
* Automatic API documentation
* Built-in request validation
* Database abstraction
* Pagination support
* Dependency injection
* Testable architecture
* Extensible backend design

---

# 🔮 Future Improvements

Potential extensions include:

* JWT authentication
* Role-based authorization
* API rate limiting
* Dockerized deployment
* PostgreSQL production setup
* Redis caching
* CI/CD with GitHub Actions
* API monitoring
* Structured application logging
* Automated API performance testing
* Cloud deployment using AWS

---

# 🎓 Learning Outcomes

This project demonstrates practical knowledge of:

* Python backend development
* FastAPI
* REST API architecture
* CRUD operations
* Database integration
* ORM concepts
* Dependency injection
* API validation
* Pagination
* OpenAPI documentation
* Automated testing
* Integration testing
* Modular software architecture
* Error handling

---

# 💼 Project Relevance

This project is relevant to roles such as:

* Python Developer
* Backend Developer
* FastAPI Developer
* Software Engineer
* API Developer
* Data Engineer
* Full Stack Developer

---

# ⚠️ Attribution

This repository is based on the open-source **FastAPI CRUD Router** project and its associated implementation and documentation.

The original project and its contributors retain rights to their respective source code and documentation. This repository is maintained for educational and portfolio-learning purposes.

Please refer to the included `LICENSE` file for the applicable license terms.

---

# 👨‍💻 Author

**Vinath M**

B.E. Computer Science and Engineering

Areas of interest:

* Python Development
* Backend Development
* FastAPI
* REST APIs
* Data Engineering
* Data Analytics
* Machine Learning
* Artificial Intelligence

---

## ⭐ Summary

**FastAPI Automated CRUD API Framework** demonstrates how modern Python backend applications can reduce repetitive CRUD development through reusable API routing, database integration, validation, pagination, documentation, and automated testing.
