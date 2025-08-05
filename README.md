# Blog Pessoal - CRUD API with Spring Boot

This is a CRUD RESTful API project developed during the Generation Brazil Bootcamp using Java and Spring Boot. It simulates a simple blogging platform with user authentication, posts, and topic management.

---

## 🚀 Technologies

- Java 17
- Spring Boot
- Spring Web / Data JPA / Security
- Hibernate
- JWT (JSON Web Token)
- PostgreSQL (or compatible RDBMS)
- Maven

---

## ⚙️ Features

- ✅ User registration, login, and update with JWT authentication
- ✅ Create, read, update, and delete blog posts
- ✅ Create, read, update, and delete related topics
- ✅ Password encryption using BCrypt
- ✅ Secure endpoints with token validation

---

## 📌 API Endpoints

### 🔐 User Authentication
| Method | Route                      | Description                    |
|--------|----------------------------|--------------------------------|
| POST   | `/usuarios/logar`          | Authenticate user and return JWT token |
| POST   | `/usuarios/cadastrar`      | Register a new user            |
| PUT    | `/usuarios/atualizar`      | Update user information        |
| GET    | `/usuarios/all`            | Get all users                  |
| GET    | `/usuarios/{id}`           | Get user by ID                 |
| GET    | `/usuarios/usuario/{usuario}` | Get user by username        |

### 📝 Post Management
| Method | Route                         | Description                  |
|--------|-------------------------------|------------------------------|
| GET    | `/postagens`                  | List all posts               |
| GET    | `/postagens/{id}`             | Get post by ID               |
| GET    | `/postagens/titulo/{titulo}`  | Search posts by title        |
| POST   | `/postagens`                  | Create a new post            |
| PUT    | `/postagens`                  | Update an existing post      |
| DELETE | `/postagens/{id}`             | Delete a post by ID          |

### 🏷️ Topic Management
| Method | Route                               | Description                |
|--------|--------------------------------------|----------------------------|
| GET    | `/temas`                             | List all topics            |
| GET    | `/temas/{id}`                        | Get topic by ID            |
| GET    | `/temas/descricao/{descricao}`       | Search topics by description |
| POST   | `/temas`                             | Create a new topic         |
| PUT    | `/temas`                             | Update an existing topic   |
| DELETE | `/temas/{id}`                        | Delete a topic by ID       |

---

## 🔐 Authenticated Requests

All protected endpoints require a JWT token in the request header:
Authorization: Bearer <your_token_here>

Example login:

```http
POST /usuarios/logar
Content-Type: application/json

{
  "usuario": "email@example.com",
  "senha": "123456"
}
```

---

## ▶️ Running Locally

### Prerequisites

- Java 17 installed
- Maven installed
- PostgreSQL running and configured
- IDE (e.g. IntelliJ, Eclipse, VSCode)

### Configuration

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/blogpessoal.git
   cd blogpessoal
   ```
2. Configure the database in src/main/resources/application.properties:

spring.datasource.url=jdbc:postgresql://localhost:5432/blogpessoal
spring.datasource.username=your_db_user
spring.datasource.password=your_db_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

3. Build and run:
```bash
 mvn spring-boot:run
```

5. Access the API at:
```bash
http://localhost:8080
```





